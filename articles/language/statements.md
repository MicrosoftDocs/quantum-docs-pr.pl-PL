---
title: 'Instrukcje Q #'
description: 'Dowiedz się więcej o poprawnym użyciu instrukcji w Q #, w tym deklaracji funkcji i operacji, deklaracjach zmiennych i przypisaniach oraz wywołaniach operacji.'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e801a5fdd24b973f47d23d2aca6f11bbebf333d4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904676"
---
# <a name="statements-and-other-constructs"></a>Instrukcje i inne konstrukcje

## <a name="comments"></a>Komentarze

Komentarze zaczynają się od dwóch ukośników, `//`i kontynuować do końca wiersza.
Komentarz może pojawić się w dowolnym miejscu w pliku źródłowym Q #.

### <a name="documentation-comments"></a>Komentarze dokumentacji

Komentarze zaczynające się od trzech ukośników, `///`, są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.
W takim przypadku ich zawartość jest pobierana jako Dokumentacja dla zdefiniowanego lub zdefiniowanego przez użytkownika typu, tak jak w przypadku innych języków .NET.

W `///` komentarzach tekst, który ma być [wyświetlany jako część](https://daringfireball.net/projects/markdown/syntax)dokumentacji interfejsu API, jest sformatowany jako przestawny, a różne części dokumentacji są wskazywane przez nagłówki o specjalnej nazwie.
Jako rozszerzenie do promocji, odwołania krzyżowe do operacji, funkcji i typów zdefiniowanych przez użytkownika w Q # można uwzględnić przy użyciu `@"<ref target>"`, gdzie `<ref target>` jest zastępowana przez w pełni kwalifikowaną nazwę obiektu kodu, do którego się odwołuje.
Opcjonalnie aparat dokumentacji może również obsługiwać dodatkowe rozszerzenia promocji.

Na przykład:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Następujące nazwy są rozpoznawane jako nagłówki komentarzy do dokumentacji.

- **Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji albo do celu typu. Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu. Powinien być zwykły tekst.
- **Opis**: Opis zachowania funkcji lub operacji lub do celu typu. Podsumowanie i opis są łączone w celu utworzenia wygenerowanego pliku dokumentacji dla funkcji, operacji lub typu.
  Opis może zawierać symbole i równania sformatowane w wierszu.
- **Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.
  Może zawierać dodatkowe podsekcje promocji wskazujące każdy pojedynczy element spójnej kolekcji wejściowej.
- **Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.
- **Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.
- **Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.
- **Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.
- **Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.
- **Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.

## <a name="namespaces"></a>Przestrzenie nazw

Każda operacja Q #, funkcja i typ zdefiniowany przez użytkownika są zdefiniowane w przestrzeni nazw.
Pytania i odpowiedzi są zgodne z tymi samymi regułami dotyczącymi nazewnictwa w innych językach .NET.
Jednak polecenie Q # nie obsługuje względnych odwołań do przestrzeni nazw.
Oznacza to, że jeśli obszar nazw `a.b` został otwarty, odwołanie do nazw operacji `c.d` nie zostanie rozpoznane do operacji z pełną nazwą `a.b.c.d`.

W bloku przestrzeni nazw dyrektywa `open` może służyć do zaimportowania wszystkich typów i żądanych, zadeklarowanych w określonej przestrzeni nazw i odwołujących się do nich według ich nazwy niekwalifikowanej. Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę. Dyrektywa `open` ma zastosowanie do całego bloku przestrzeni nazw w pliku.

Typ lub możliwy do odłożenia zdefiniowany w innej przestrzeni nazw, który nie jest otwarty w bieżącej przestrzeni nazw, musi odwoływać się do jego w pełni kwalifikowanej nazwy.
Na przykład operacja o nazwie `Op` w przestrzeni nazw `X.Y` musi być odwołująca się do w pełni kwalifikowanej nazwy `X.Y.Op`, chyba że przestrzeń nazw `X.Y` została otwarta wcześniej w bieżącym bloku. Jak wspomniano powyżej, nawet jeśli `X` przestrzeń nazw została otwarta, nie można odwołać się do operacji jako `Y.Op`.
Jeśli w tej przestrzeni nazw i pliku została zdefiniowana `Z` krótka nazwa `X.Y`, `Op` musi być określana jako `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Zwykle lepiej jest dołączyć przestrzeń nazw za pomocą dyrektywy `open`.
Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.

## <a name="formatting"></a>Formatowanie

Większość instrukcji i dyrektyw Q # kończy się średnikiem, `;`.
Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji nie wymagają kończącego się średnika.
Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.

Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, mogą być rozbite w wielu wierszach.
Należy unikać wielu instrukcji w pojedynczym wierszu.

## <a name="statement-blocks"></a>Bloki instrukcji

Instrukcje Q # są pogrupowane w bloki instrukcji.
Blok instrukcji rozpoczyna się od otwierającego `{` i zamyka `}`zamknięcia.

Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.

## <a name="symbol-binding-and-assignment"></a>Powiązanie symboli i przypisanie

Q # rozróżnia symbole modyfikowalne i zmienne.
Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.

Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.

Ponieważ wszystkie typy Q # są typami wartości — przy użyciu qubits, który ma nieco specjalną rolę — jest tworzona "kopia", gdy wartość jest powiązana z symbolem lub gdy jest on powiązany. Oznacza to, że zachowanie Q # jest takie samo, jak w przypadku tworzenia kopii podczas przypisywania. Dotyczy to również tablic. Oczywiście w praktyce tylko odpowiednie fragmenty są w rzeczywistości odtworzone w razie potrzeby. 

### <a name="tuple-deconstruction"></a>Dekonstrukcja krotki

Jeśli po prawej stronie powiązania jest krotka, ta krotka może zostać rozbudowana po przypisaniu.
Takie dekonstrukcji mogą dotyczyć krotek zagnieżdżonych, a każda pełna lub częściowa dekonstrukcja jest prawidłowa, o ile kształt krotki po prawej stronie jest zgodny z kształtem krotki symboli.
Funkcję dekonstrukcja krotki można szczególnie użyć, gdy po prawej stronie `=` jest wyrażenie wartości krotek.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Niezmienne symbole

Zmienne symbole są powiązane przy użyciu instrukcji `let`.
Jest to przybliżenie równoważne deklaracji zmiennej i inicjalizacji w językach takich jak C#, z wyjątkiem tego, że symbole Q #, po powiązaniu, nie mogą być zmieniane; powiązania `let` są niezmienne.

Niezmienne powiązanie składa się ze słowa kluczowego `let`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do powiązania symboli z i kończące się średnikiem.
Typ powiązanych symboli jest wywnioskowany na podstawie wyrażenia z prawej strony.

### <a name="mutable-symbols"></a>Symbole modyfikowalne

Symbole modyfikowalne są zdefiniowane i inicjowane przy użyciu instrukcji `mutable`.
Symbole zadeklarowane i powiązane jako część instrukcji `mutable` mogą być ponownie powiązane z inną wartością w kodzie. 

Modyfikowalna instrukcja powiązania składa się ze słowa kluczowego `mutable`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do powiązania symboli z i kończący średnik.
Typ powiązanych symboli jest wywnioskowany na podstawie wyrażenia z prawej strony. Jeśli symbol zostanie powiązana później w kodzie, jego typ nie ulegnie zmianie, a wartość związana musi być zgodna z tym typem.

### <a name="rebinding-of-mutable-symbols"></a>Ponowne wiązanie modyfikowalnych symboli

Zmienna modyfikowalna może być powiązana przy użyciu instrukcji `set`.
Takie ponowne powiązanie składa się ze słowa kluczowego `set`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do ponownego powiązania symboli z i kończące się średnikiem.
Wartość musi być zgodna z typem (-ami) symboli, z którymi jest powiązane.

#### <a name="apply-and-reassign-statement"></a>Instrukcja Apply-and-Reassign

Szczególnym typem instrukcji Set, do których odwołuje się jako instrukcja Apply-and-Reassign, stanowi wygodny sposób łączenia, jeśli prawa strona składa się z aplikacji operatora binarnego, a wynik ma być ponownie powiązany z lewym argumentem operatora. Na przykład:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
zwiększa wartość licznika `counter` w każdej iteracji pętli `for`. Powyższy kod jest równoważny z 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ po lewej stronie jest zgodny z typem wyrażenia. Pozwala to na przykład wygodny sposób na gromadzenie wartości:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Instrukcja Update-and-Reassign

Podobne złączenie istnieje dla wyrażeń Copy-and-Update z prawej strony. Istnieją odpowiednie instrukcje Update-and-Reassign dla nazwanych elementów w typach zdefiniowanych przez użytkownika, a także dla elementów tablicy.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

W przypadku tablic nasze biblioteki standardowe zawierają niezbędne narzędzia do wykonywania wielu typowych operacji inicjalizacji i manipulowania tablicami, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu. Instrukcje Update-and-Reassign oferują alternatywę w razie konieczności:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> Unikaj niepotrzebnego stosowania instrukcji Update-and-Reassign, wykorzystując narzędzia dostarczone w <xref:microsoft.quantum.arrays>.

Funkcja
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
na przykład można po prostu uprościć przy użyciu funkcji `ConstantArray` w `Microsoft.Quantum.Arrays`i zwrócić wyrażenie Copy-and-Update:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Zakresy powiązań

Ogólnie rzecz biorąc, powiązania symboli wykraczają poza zakres i stają się nieaktywne na końcu bloku instrukcji, w którym występują.
Istnieją dwa wyjątki od tej reguły:

- Powiązanie zmiennej pętli pętli `for` jest w zakresie dla treści pętli for, ale nie po końcu pętli.
- Wszystkie trzy części `repeat`/pętla `until` (treść, test i naprawa) są traktowane jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.

W przypadku obu typów pętli każdy przechodzi przez pętlę do własnego zakresu, dlatego powiązania z wcześniejszych przebiegów nie są dostępne w późniejszym przebiegu.

Powiązania symboli z bloków zewnętrznych są dziedziczone przez bloki wewnętrzne.
Symbol może być powiązany tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").
Następujące sekwencje byłyby dozwolone:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

i

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

Może to jednak być niedozwolone:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

w takim przypadku:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>Przepływ sterowania

### <a name="for-loop"></a>Pętla for

Instrukcja `for` obsługuje iterację w zakresie liczb całkowitych lub za pośrednictwem tablicy.
Instrukcja składa się z słowa kluczowego `for`, otwierającego nawiasu `(`, po którym następują krotka symboli lub symboli, słowo kluczowe `in`, wyrażenie typu `Range` lub Array, `)`nawias zamykające i blok instrukcji.

Blok instrukcji (treść pętli) jest wykonywany wielokrotnie ze zdefiniowanymi symbolami (zmienne pętli) powiązane z każdą wartością w zakresie lub tablicy.
Należy pamiętać, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie zostanie wykonana.
Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się podczas wykonywania pętli.

Powiązanie zadeklarowanych symboli jest niezmienne i zgodne z tymi samymi regułami, co inne powiązania zmiennych. W szczególności możliwe jest, aby można było zadestruktorować, np. elementy array dla iteracji przez tablicę po przypisaniu do zmiennych pętli.

Na przykład:

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Zmienna pętla jest powiązana z każdym wejściem do treści pętli i niezależna na końcu treści.
W szczególności zmienna Loop nie jest powiązana po zakończeniu pętli for.

### <a name="repeat-until-success-loop"></a>Pętla REPEAT-until-Success

Instrukcja `repeat` obsługuje wzorzec "Repeat to until".
Składa się ze słowa kluczowego `repeat`, po którym następuje blok instrukcji (treść _pętli_ ), słowo kluczowe `until`, wyrażenie logiczne, a kończące się średnik lub słowo kluczowe `fixup` następuje inny blok instrukcji ( _Naprawa_).
Treść pętli, warunek i naprawa są uważane za pojedynczy zakres, dlatego symbole powiązane z treścią są dostępne w warunku i naprawienia.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

Zostanie wykonana treść pętli, a następnie warunek jest obliczany.
Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie nastąpi wykonanie naprawy, a instrukcja jest wykonywana ponownym uruchomieniem, rozpoczynając od treści pętli.
Należy zauważyć, że Kończenie wykonywania naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.

Na przykład poniższy kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ przy użyciu bram Hadamard i T.
Pętla kończy się w $ \frac{8}{5}$ powtórzy się średnio.
Aby uzyskać szczegółowe informacje, zobacz [*REPEAT-until-Success: niedeterministyczna dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji. Odpowiednie funkcje są udostępniane przez pętle w funkcjach. 

### <a name="while-loop"></a>While — pętla

Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum. Są one powszechnie używane w określonych klasach algorytmów Quantum — a tym samym — dedykowana konstrukcja języka w Q #. Jednak pętle, które są przerywane w zależności od warunku, a długość wykonywania jest w tym przypadku nieznana w czasie kompilacji, muszą być obsługiwane z uwzględnieniem szczególnych informacji w środowisku uruchomieniowym Quantum. Ich użycie w ramach funkcji z drugiej strony jest nieproblematyczne, ponieważ tylko zawierają kod, który będzie wykonywany na konwencjonalnym sprzęcie (innym niż Quantum). 

W związku z tym funkcja Q # obsługuje używanie pętli while tylko wewnątrz funkcji. Instrukcja `while` składa się ze słowa kluczowego `while`, otwierającego nawiasu `(`, warunku (tj. wyrażenia logicznego), nawiasu zamykającego `)`i bloku instrukcji.
Blok instrukcji (treść pętli) jest wykonywany tak długo, jak warunek oblicza `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Instrukcja warunkowa

Instrukcja `if` obsługuje wykonywanie warunkowe.
Składa się ze słowa kluczowego `if`, otwartego nawiasu `(`, wyrażenia logicznego, nawiasu zamykającego `)`i bloku instrukcji (bloku _then_ ).
Może to być dowolna liczba klauzul innych niż IF, z których każdy składa się ze słowa kluczowego `elif`, otwierającego nawiasu `(`, wyrażenia logicznego, nawiasu zamykającego `)`i bloku instrukcji (bloku _else-if_ ).
Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się z słowa kluczowego `else`, po którym następuje inny blok instrukcji ( _else_ Block).
Warunek jest obliczany, a jeśli ma wartość true, zostaje wykonany blok then.
Jeśli warunek ma wartość false, zostanie obliczony pierwszy warunek else-if; Jeśli wartość jest równa true, ten blok else-IF jest wykonywany.
W przeciwnym razie drugi blok else-if zostanie przetestowany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.
Jeśli oryginalny warunek if i wszystkie klauzule else-if mają wartość false, blok else jest wykonywany, jeśli został podany.

Należy zauważyć, że każdy blok jest wykonywany we własnym zakresie.
Powiązania wykonane wewnątrz bloku Then, Else-if lub else nie są widoczne po zakończeniu instrukcji if.

Na przykład:

```qsharp
if (result == One) {
    X(target);
} 
```

lub

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Przesłać

Instrukcja return kończąca wykonywanie operacji lub funkcji i zwraca wartość do obiektu wywołującego.
Składa się ze słowa kluczowego `return`, po którym następuje wyrażenie odpowiedniego typu i kończący średnik.

Wywoływanie, które zwraca pustą krotkę, `()`, nie wymaga instrukcji return.
Jeśli pożądane jest wczesne wyjście, w tym przypadku można użyć `return ()`.
Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.

W obrębie operacji nie ma maksymalnej liczby instrukcji return.
Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.

Na przykład:

```qsharp
return 1;
```

lub

```qsharp
return ();
```

lub

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Niepowodzenie

Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.
Składa się ze słowa kluczowego `fail`, po którym następuje ciąg i kończący się średnik.
Ten ciąg jest zwracany do klasycznego sterownika jako komunikat o błędzie.

W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.
Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.

Na przykład:

```qsharp
fail $"Impossible state reached";
```

lub

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit Management

Należy zauważyć, że żadna z tych instrukcji nie jest dozwolona w treści funkcji.
Są one prawidłowe tylko w obrębie operacji.

### <a name="clean-qubits"></a>Wyczyść Qubits

Instrukcja `using` jest używana do pozyskiwania nowych qubits do użycia w bloku instrukcji.
Qubits jest gwarantowany do zainicjowania w stanie `Zero` obliczeniowym.
Qubits powinien być w stanie `Zero` obliczeniowym na końcu bloku instrukcji; symulatory są zachęcane do wymuszenia tego.

Instrukcja składa się z słowa kluczowego `using`, po którym następuje otwarty nawias `(`, powiązanie, nawias zamykający `)`oraz blok instrukcji, w ramach którego będzie dostępny qubits.
Powiązanie jest zgodne z tym samym wzorcem co `let` instrukcji: pojedynczy symbol lub krotka symboli, po którym następuje znak równości `=`i pojedyncza wartość lub zgodna krotka dla inicjatorów.
Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()`, lub tablicy qubits, wskazywanym przez `Qubit[`, wyrażenie `Int` i `]`.

Na przykład:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Zapożyczony Qubits

Instrukcja `borrowing` służy do uzyskania qubits do tymczasowego użycia. Instrukcja składa się z słowa kluczowego `borrowing`, po którym następuje otwarty nawias `(`, powiązanie, nawias zamykający `)`oraz blok instrukcji, w ramach którego będzie dostępny qubits.
Powiązanie jest zgodne z tym samym wzorcem i regułami, co w instrukcji `using`.

Na przykład:

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.
Pożyczkobiorca zatwierdzi, aby opuszczał qubits w tym samym stanie, w którym były zapożyczone, tj. ich stan na początku i na końcu bloku instrukcji powinien być taki sam.
Ten stan w szczególności nie jest stanem klasycznym, takim jak w większości przypadków, zakresy pożyczek nie powinny zawierać pomiarów. 

Zobacz [*Refaktoryzacja przy użyciu 2n + 2 qubits z użyciem mnożenia modularnego Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017), aby zobaczyć przykład zapożyczonego użycia qubit.

Podczas pożyczania qubits system najpierw spróbuje wypełnić żądanie z qubits, które są używane, ale nie są dostępne w treści instrukcji `borrowing`.
Jeśli nie ma wystarczającej ilości takich qubits, przydzieli nowe qubits do wykonania żądania.

## <a name="conjugations"></a>Liczby sprzężone

W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled. Można to uniknąć przez prawidłowe wykonanie obliczeń przed zwolnieniem pamięci. Typowym wzorcem przetwarzania Quantum jest następujące: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: Nowość: Rozpoczynanie pracy z naszym wydaniem 0,9, obsługujemy instrukcję sprzężenia, która implementuje przekształcenie powyżej. Korzystając z tej instrukcji, `ApplyWith` operacji można zaimplementować w następujący sposób:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Taka instrukcja sprzężona oczywiście jest znacznie bardziej użyteczna, jeśli transformacja zewnętrzna i wewnętrzna nie jest łatwo dostępna jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji. 

Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i wykonywane po zakończeniu stosu Apply. Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku. 

## <a name="expression-evaluation-statements"></a>Instrukcje oceny wyrażeń

Jako instrukcji można użyć dowolnego wyrażenia wywołania typu `Unit`.
Jest to głównie używane podczas wywoływania operacji na qubits, które zwracają `Unit`, ponieważ celem instrukcji jest zmodyfikowanie niejawnego stanu Quantum.
Instrukcje oceny wyrażeń wymagają zakończenia średnika.

Na przykład:

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
