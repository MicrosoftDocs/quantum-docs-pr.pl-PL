---
title: 'Techniki Q # — operacje i funkcje | Microsoft Docs'
description: 'Metody Q # — operacje i funkcje'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183458"
---
# <a name="q-operations-and-functions"></a>Operacje i funkcje pytań i odpowiedzi

Programy Q # składają się z jednej lub wielu *operacji* , które opisują efekty uboczne działania Quantum mogą mieć na dane Quantum oraz co najmniej jedną *funkcję* , która zezwala na modyfikacje danych klasycznych. W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie klasycznego zachowania i nie mają żadnych efektów poza obliczaniem klasycznej wartości wyjściowej.

Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi operacjami wewnętrznymi zdefiniowanymi przez język. Określony sposób, w jaki te operacje wewnętrzne są zdefiniowane, zależy od maszyny docelowej. Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.

## <a name="defining-new-operations"></a>Definiowanie nowych operacji

Jak opisano powyżej, najbardziej podstawowy blok konstrukcyjny w programie Quantum Zapisano w Q # jest *operacją*, którą można wywołać z klasycznej aplikacji .NET, np. za pomocą symulatora lub przez inne operacje w usłudze Q #.
Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.
Na przykład następująca operacja definiuje tylko domyślną specjalizację treści i przyjmuje pojedyncze qubit jako dane wejściowe, a następnie wywołuje wbudowaną operację `X` na tym wejściu:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Słowo kluczowe `operation` rozpoczyna definicję operacji, a po niej następuje nazwa; tutaj `BitFlip`.
Następnie typ danych wejściowych jest zdefiniowany jako `Qubit`, wraz z nazwą `target` do odwoływania się do danych wejściowych w ramach nowej operacji.
Podobnie `Unit` definiuje, że dane wyjściowe operacji są puste.
Jest to podobne do `void` w C# i innych językach bezwzględnych i jest równoważne `unit` w F# i innych językach funkcjonalnych.

> [!NOTE]
> Szczegółowo omówiono poniżej, ale każda operacja w Q # przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.
> Dane wejściowe i wyjściowe są następnie reprezentowane przy użyciu *krotek*, które zbierają wiele wartości w jedną wartość.
> Nieformalnie Załóżmy, że Q # to język "Krotka w poziomie".
> Po tym koncepcji `()` powinna zostać odczytana jako spójna krotka, która ma typ `Unit`.

W ramach nowej operacji implementacja może być określona bezpośrednio w deklaracji, jeśli tylko implementacja specjalizacji treści domyślnej musi być określona jawnie. Ponadto można zdefiniować implementacje programu, na przykład jedną lub więcej operacji `functor`, jak zostało to opisane poniżej. W powyższym przykładzie jedyną instrukcją jest wywołanie wbudowanej operacji Q # <xref:microsoft.quantum.intrinsic.x>.

Operacje mogą również zwracać bardziej interesujące typy niż `Unit`.
Na przykład operacja <xref:microsoft.quantum.intrinsic.m> zwraca dane wyjściowe typu `Result`, co oznacza, że przeprowadzono pomiar. Możemy przekazać dane wyjściowe operacji do innej operacji lub użyć jej przy użyciu słowa kluczowego `let`, aby zdefiniować nową zmienną.
<!-- Link to UID for superdense conceptual and example documentation. -->
Pozwala to na reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku kodowania w stojaku:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Funktory, sąsiadujące i kontrolowane
Jeśli operacja implementuje transformację jednostkową, można zdefiniować sposób działania operacji przy *adjointed* lub *kontrolowanej*. Podległych specjalizacja operacji określa, jak działa po uruchomieniu w odwrotnym czasie, podczas kontrolowanej specjalizacji określa sposób działania operacji po zastosowaniu warunku na stanie rejestru Quantum.
Istnienie tych specjalizacji może być zadeklarowane jako część sygnatury operacji: `is Adj + Ctl` w poniższym przykładzie. Odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest generowana przez kompilator. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Wiele operacji w Q # reprezentuje bramy jednostkowe.
> Jeśli $U $ jest bramą jednostkową reprezentowaną przez operację `U`, wówczas `Adjoint U` reprezentuje bramę jednostkową $U ^ \dagger $.

W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić. Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej dyrektywy generacji lub implementacji zdefiniowanej przez użytkownika. Kod w `PrepareEntangledPair` powyżej na przykład jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.
Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
W powyższym przykładzie `adjoint invert;` wskazuje, że podległych specjalizacji ma być generowana przez odwrócenie implementacji treści, a `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowany przez odwrócenie danej implementacji kontrolowana specjalizacja.

Zobaczymy więcej przykładów tego elementu w [przepływie sterowania wyższej kolejności](xref:microsoft.quantum.concepts.control-flow).

Aby wywołać specjalizację operacji, użyj słowa kluczowego `Adjoint` lub `Controlled`.
Na przykład powyższy przykładowy przykład kodowania można napisać bardziej kompaktowo, używając sąsiadującego `PrepareEntangledPair` do przekształcenia stanu Entangled z powrotem do pary unentangled qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Istnieje kilka ważnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.
W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji nie może być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.


## <a name="defining-new-functions"></a>Definiowanie nowych funkcji

Funkcja Q # umożliwia także Definiowanie *funkcji*, które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.
W szczególności funkcje nie mogą wywoływać operacji, działać na qubits, przykładowe liczby losowe lub w inny sposób zależały od stanu poza wartością wejściową do funkcji.
W związku z tym funkcje Q # są *czyste*, w tym przypadku zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.
Dzięki temu kompilator Q # może bezpiecznie zmienić kolejność i czas wywoływania funkcji podczas generowania specjalizacji operacji.

Definiowanie funkcji działa podobnie do definiowania operacji, z tą różnicą, że dla funkcji nie można definiować podległych lub kontrolowanych specjalizacji.
Na wystąpienie:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu można łatwiej używać jej w ramach operacji.
Jeśli firma Microsoft zapisała `Square` w ramach operacji, na przykład kompilator nie może zagwarantować, że wywołanie go z tym samym danymi wejściowymi będzie spójnie generować te same dane wyjściowe.

Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych, z poziomu operacji Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Za każdym razem, gdy `U` jest wywoływana, będzie ona mieć inną akcję na `target`.
W szczególności kompilator nie może zagwarantować, że w przypadku dodania do `U`deklaracji specjalizacji `adjoint auto`, `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).
Jest to naruszone w przypadku [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors), co pozwala na automatyczne generowanie podległych specjalizacji w operacji, w których wywołano operację, <xref:microsoft.quantum.math.randomreal> spowodują przerwanie gwarancji dostarczonych przez kompilator ; <xref:microsoft.quantum.math.randomreal> to operacja, dla której nie istnieje przyległych lub kontrolowana wersja.

Z drugiej strony, zezwolenie na wywołania funkcji, takie jak `Square`, jest bezpieczne, w tym przypadku kompilator może mieć pewność, że tylko dane wejściowe są zachowywane `Square` w celu zapewnienia stabilności danych wyjściowych.
W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.

## <a name="control-flow"></a>Przepływ sterowania

W ramach operacji lub funkcji każda instrukcja jest wykonywana w kolejności, podobnie jak w przypadku najczęściej używanych języków klasycznych.
Ten przepływ sterowania można jednak zmodyfikować na trzy różne sposoby:

- Instrukcje `if`
- Pętle `for`
- `repeat`-`until` pętle

Wykorzystamy z tej ostatniej dyskusji, dopóki nie będziemy omawiać powtarzających się obwodów [(jednostek ru)](xref:microsoft.quantum.techniques.qubits#measurements) .
Konstrukcje `if` i `for` sterowania przepływem, jednak należy pamiętać o najbardziej znanym znaczeniu dla większości klasycznych języków programowania.
W szczególności instrukcja `if` może wykonać jedną lub więcej instrukcji `elif` i może kończyć się `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Podobnie pętle `for` wskazują iterację w zakresie liczb całkowitych lub na elementy tablicy:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Należy pamiętać, że `for` pętle i instrukcje `if` mogą być również używane w operacjach, dla których specjalizacje są generowane automatycznie. W takim przypadku sąsiadująca pętla `for` odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.
Ta zasada jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczanie w ramach SOCKS, a następnie odbuty, musisz cofnąć umieszczanie na butów, a następnie cofnąć umieszczenie w usłudze SOCKS.
Decidedly mniej dobrze, aby wypróbować i podjąć Twoje SOCKS, gdy będziesz nadal korzystać z swoich oddziałów.

## <a name="operations-and-functions-as-first-class-values"></a>Operacje i funkcje jako wartości pierwszej klasy

Jedną z kluczowych technik z przyczyn dotyczących przepływu sterowania i klasycznej logiki przy użyciu funkcji, a nie operacji, jest wykorzystanie tych operacji i funkcji w Q # są *pierwszą klasą*.
Oznacza to, że są to poszczególne wartości w języku we własnym zakresie.
Na przykład, poniżej jest doskonale prawidłowy kod Q #, w przypadku niewielkiego pośrednika:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Wartość zmiennej `ourH` w powyższym fragmencie kodu jest wtedy operacją <xref:microsoft.quantum.intrinsic.h>, dzięki czemu możemy wywołać tę wartość, podobnie jak każda inna operacja.
Dzięki temu możemy pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.
Na przykład możemy Wyobraź sobie, że chcemy "kwadratowych" operacji, stosując ją dwa razy do tego samego elementu docelowego qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

W tym przykładzie strzałka `=>`, która pojawia się w typie `(Qubit => Unit)` oznacza, że pole wejściowe `op` jest operacją, która przyjmuje jako dane wejściowe typ `Qubit` i tworzy pustą krotkę jako wyjściową.
Dodatkowo określimy cechy tego typu operacji, które zawierają informacje o tym, które funktory są obsługiwane.
Operacja typu `(Qubit => Unit)` nie obsługuje `Adjoint` ani `Controlled` Funktor. Jeśli chcemy wskazać, że operacja tego typu musi obsługiwać np. `Adjoint` Funktor, musimy zadeklarować ją jako sąsiedniej. Jest to realizowane przy użyciu adnotacji `is Adj` do typu. Podobnie `(Qubit => Unit is Ctl)` oznacza, że operacja tego typu obsługuje `Controlled` Funktor. Zapoznajemy się z tym tematem, aby poznać [typy w Q #] (linki XREF: Microsoft. Quantum. Language. Type-model) bardziej ogólnie.

Teraz przykro, że możemy również zwrócić operacje w ramach danych wyjściowych, aby można było izolować niektóre rodzaje klasycznej logiki warunkowej jako klasyczną funkcję, która zwraca opis programu Quantum w postaci operacji.
W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.
Możemy napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołamy ją z tymi samymi wartościami `hereBit` i `thereBit`, zawsze będziemy wrócić do tej samej operacji.
W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.
Oznacza to, że w funkcji jest izolowana klasyczna logika, która gwarantuje, że wywołanie funkcji można zmienić przy użyciu impunity, tak długo, jak dane wejściowe są zachowywane.

Możemy również traktować funkcje jako wartości pierwszej klasy, ponieważ w przypadku omawianych [typów operacji i funkcji](#operations-and-functions-as-first-class-values)zostanie wyświetlony bardziej szczegółowy.

## <a name="partially-applying-operations-and-functions"></a>Częściowo stosowane operacje i funkcje

Możemy znacznie bardziej robić dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji*, w którym możemy dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania. Na przykład odwołując się do powyższego przykładu `ApplyTwice`, możemy wskazać, że nie chcemy określać, od razu, do czego qubit operacja wejścia powinna być stosowana:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

W takim przypadku zmienna lokalna `twiceOp` przechowuje częściowo zastosowana operacja `ApplyTwice(op, _)`, w przypadku których części danych wejściowych, które nie zostały jeszcze określone, są wskazywane przez `_`.
Gdy faktycznie wywołamy `twiceOp` w następnym wierszu, przekazujemy jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.
W związku z tym Powyższy fragment kodu jest efektywnie identyczny z nazwą, która jest bezpośrednio wywoływana `ApplyTwice(op, target)`, a następnie Zapisz, że wprowadziliśmy nową zmienną lokalną, która pozwala na opóźnienie wywołania podczas udostępniania niektórych części danych wejściowych.

Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu udostępnienia całego danych wejściowych, możemy bezpiecznie zastosować operacje nawet z poziomu funkcji.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

W zasadzie klasyczna logika w ramach `SquareOperation` może być znacznie większa, ale nadal odizolowana od pozostałej części operacji przez gwarancje, które kompilator może zaoferować na temat funkcji.
Ta metoda zostanie użyta w całej standardowej bibliotece Q # do wyrażenia klasycznego przepływu sterowania w sposób, który może być łatwo używany w ramach programów Quantum.
