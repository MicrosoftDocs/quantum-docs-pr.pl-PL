---
title: Dalsze wprowadzenie do technik pytań i odpowiedzi
description: 'Zapoznaj się z tematami dotyczącymi zaawansowanych tematów w sekcji Q #, takich jak tworzenie ogólnych funkcji i pożyczanie qubits.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 46ebf544c1d6e56f152a06d06151305fa972011a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906903"
---
# <a name="going-further"></a>Dalsze przechodzenie #

Teraz, gdy wiesz już, jak pisać interesujące programy Quantum w Q #, ta sekcja jest bardziej wydajna, wprowadzając kilka bardziej zaawansowanych tematów, które powinny być przydatne w przyszłości.


## <a name="generic-operations-and-functions"></a>Operacje ogólne i funkcje ##

> [!TIP]
> W tej sekcji przyjęto założenie, że podstawowa znajomość metod [ogólnych C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [ F#w programie ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ szablonów](https://docs.microsoft.com/cpp/cpp/templates-cpp)lub podobnych podejścia do programowania w innych językach.

Wiele funkcji i operacji, które firma Microsoft może chcieć zdefiniować, nie opiera się na typach ich danych wejściowych, ale raczej niejawnie używa ich typów za pośrednictwem innej funkcji lub operacji.
Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $\{x_1, x_2, \dots, x_n\}$, map zwraca nową kolekcję $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
W celu zaimplementowania tego zadania w programie Q # można skorzystać z tej funkcji jako pierwszej klasy.
Napiszmy do krótkiego przykładu `Map`przy użyciu ★ jako symbolu zastępczego, aby określić, jakich typów potrzebujemy.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie rzeczywiste typy zostały zastąpione.
Mapa z liczb całkowitych na Paul, na przykład, wygląda podobnie jak mapa od liczb zmiennoprzecinkowych do ciągów:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

W zasadzie można napisać wersję `Map` dla każdej pary typów, które napotykamy, ale wprowadzamy wiele problemów.
Na przykład jeśli znajdziesz usterkę w `Map`, należy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach `Map`.
Ponadto, jeśli tworzymy nową krotkę lub UDT, teraz musimy utworzyć nową `Map`, która będzie musiała być nowym typem.
Chociaż jest to pozyskanie dla niewielkiej liczby takich funkcji, ponieważ zbieramy więcej i więcej funkcji tego samego formularza co `Map`, koszt wprowadzenia nowych typów stanie się nieuzasadniony bardzo krótki.

Większość tego rodzaju trudności wynika jednak z tego, że kompilator nie udostępnił informacji, które są potrzebne do rozpoznania, w jaki sposób są powiązane różne wersje `Map`.
Efektywnie, chcemy, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z *typów* q # do funkcji q #.
Pojęcie to jest formalne przez umożliwienie funkcjom i operacjom posiadania *parametrów typu*, a także ich zwykłych parametrów krotek.
W powyższych przykładach chcemy myśleć, że `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.
W większości przypadków te parametry typu mogą być używane tak, jakby były typami zwyczajnymi: używamy wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.

> [!NOTE]
> Najbardziej skrajnym przypadkiem pośredniego zależności jest qubits, gdzie program Q # nie może bezpośrednio polegać na strukturze typu `Qubit`, ale **musi** przekazać takie typy do innych operacji i funkcji.

Powracając do powyższego przykładu, możemy zobaczyć, że potrzebujemy `Map`, aby zawierały parametry typu, jeden do reprezentowania danych wejściowych do `fn` i jeden do reprezentowania danych wyjściowych z `fn`.
W języku Q # jest to zapisywana przez dodanie nawiasów ostrych (`<>`, nie brakets $ \braket{}$!) po nazwie funkcji lub operacji w swojej deklaracji oraz przez wystawienie poszczególnych parametrów typu.
Nazwa każdego parametru typu musi rozpoczynać się od osi `'`, co oznacza, że jest parametrem typu, a nie typem zwykłym (znanym także jako *konkretny* typ).
W przypadku `Map`należy napisać:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobnie do wersji zanotowanych przed.
Jedyną różnicą jest to, że został jawnie poinformowany kompilator, że `Map` nie zależał bezpośrednio od tego, co `'Input` i `'Output` są, ale działa w przypadku każdego z dwóch typów przy użyciu ich pośrednio za pośrednictwem `fn`.
Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób możemy ją wywołać, tak jakby była to funkcja zwykła:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "krotka spójna z krotką" to bardzo użyteczny sposób, aby myśleć o funkcjach i operacjach pytań i odpowiedzi.
> Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* funkcję Q #.
> Podobnie każda operacja może zostać przeniesiona do danych wejściowych typu `'T => 'U`.

W drugim przykładzie należy wziąć pod uwagę wyzwanie napisania funkcji, która zwraca skład dwóch innych funkcji:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

W tym miejscu należy określić dokładnie `A`, `B`i `C`, a tym samym znacznie ograniczyć narzędzie do nowej funkcji `Compose`.
Po wszystkich `Compose` zależy tylko od `A`, `B`i `C` *za pośrednictwem* `innerFn` i `outerFn`.
Alternatywnie, możemy dodać parametry typu do `Compose`, które wskazują, że działa dla *każdej* `A`, `B`i `C`, tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Biblioteki Q # Standard oferują wiele takich operacji i funkcji sparametryzowanych typu, aby ułatwić przepływ sterowania wyższym kolejnością.
Są one omówione bardziej szczegółowo w [przewodniku po bibliotece standardowej Q #](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Pożyczanie Qubits ##

Mechanizm pożyczania umożliwia alokację qubits, która może być używana jako miejsce do rozliczania podczas obliczeń. Te qubits zazwyczaj nie są w stanie czystym, tzn. nie muszą być inicjowane w znanym stanie, takim jak $ \ket{0}$. Jeden również mówi "Dirty" qubits, gdy ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum. Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.

W programie Canon istnieją przykłady, które używają słowa kluczowego `borrowing`, na przykład funkcja `MultiControlledXBorrow` zdefiniowana poniżej.
Jeśli `controls` określa, że kontrolka qubits powinna zostać dodana do operacji `X`, w tej implementacji zostanie dodana ogólna `Length(controls)-2` wiele zanieczyszczonych ancillas.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Należy zauważyć, że rozległe użycie `With` Combinator---w swojej formie, która ma zastosowanie do operacji, które obsługują sąsiednie, tj., `WithA`---zostało wykonane w tym przykładzie, który jest dobrym stylem programowania, ponieważ dodawanie kontroli do struktur obejmujących `With` tylko propagowanie kontroli do operacji wewnętrznej. Należy również zwrócić uwagę, że w tym miejscu oprócz `body` operacji wdrożenie `controlled` treści operacji zostało jawnie dostarczone, a nie do instrukcji `controlled auto`. Przyczyną tego jest fakt, że wiemy ze struktury obwodu, jak łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram i każdej bramy w `body`. 

Warto porównać ten kod z inną funkcją firmy Canon `MultiControlledXClean`, która osiąga ten sam cel implementacji operacji pomnożonej `X`, ale korzysta z kilku czystych qubits przy użyciu mechanizmu `using`. 
