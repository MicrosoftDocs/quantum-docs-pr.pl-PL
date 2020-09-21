---
title: Sterowanie przepływem w Q# standardowej libararies
description: Dowiedz się więcej na temat operacji sterowania przepływem i funkcji w Q# bibliotece standardowej firmy Microsoft.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835625"
---
# <a name="higher-order-control-flow"></a>Przepływ sterowania wyższej kolejności #

Jedną z podstawowych ról standardowej biblioteki jest ułatwienie bardziej szczegółowych rozwiązań algorytmów wysokiego poziomu jako [programów Quantum](https://en.wikipedia.org/wiki/Quantum_programming).
W ten sposób Q# Canon oferuje różne różne konstrukcje sterowania przepływem, z których każdy jest zaimplementowany przy użyciu częściowego zastosowania funkcji i operacji.
Przeskocz bezpośrednio do przykładu Rozważmy przypadek, w którym jeden chce utworzyć "CNOT drabinę" w rejestrze:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Ten wzorzec można wyrazić za pomocą iteracji i `for` pętli:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<xref:microsoft.quantum.canon.applytoeachca> <xref:microsoft.quantum.arrays.zip> Jest to jednak znacznie krótsze i łatwiejsze do odczytania, wyrażone w zakresie i funkcje manipulowania tablicą, takie jak:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

W pozostałej części tej sekcji udostępnimy kilka przykładów użycia różnych operacji sterowania przepływem i funkcji dostarczonych przez Canon w celu kompaktowania ekspresowych programów Quantum.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Stosowanie operacji i funkcji w odniesieniu do tablic i zakresów ##

Jednym z podstawowych streszczeń dostarczonych przez Canon jest iteracja.
Na przykład rozważmy jednostkową część formularza $U \otimes U \otimes \cdots \otimes U $ dla $U jednostkowego dla jednej qubit $.
W programie Q# możemy użyć <xref:microsoft.quantum.arrays.indexrange> do reprezentowania tego jako `for` pętli w rejestrze:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Następnie możemy użyć tej nowej operacji, `HAll(register)` Aby zastosować $H \Otimes H \otimes \cdots \Otimes h $.

Jest to bardzo skomplikowane, ale szczególnie w większym algorytmie.
Ponadto takie podejście jest wyspecjalizowane dla konkretnej operacji, którą chcemy zastosować do każdego qubitu.
Możemy użyć faktu, że operacje są pierwszej klasy, aby bardziej szczegółowo wyrażać ten algorytm algorytmu:

```qsharp
ApplyToEachCA(H, register);
```

W tym miejscu sufiks `CA` wskazuje, że wywołanie `ApplyToEach` jest samodzielne i kontrolowane.
W tym przypadku, jeśli `U` obsługuje `Adjoint` i `Controlled` , następujące wiersze są równoważne:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

W szczególności oznacza to, że wywołania `ApplyToEachCA` mogą pojawić się w operacjach, dla których jest generowana automatycznie.
Podobnie, <xref:microsoft.quantum.canon.applytoeachindex> jest przydatne do reprezentowania wzorców formularza `U(0, targets[0]); U(1, targets[1]); ...` i oferuje wersje dla każdej kombinacji funktory obsługiwane przez dane wejściowe.

> [!TIP]
> `ApplyToEach` jest parametrem typu, który może być używany z operacjami, które pobierają dane wejściowe inne niż `Qubit` .
> Załóżmy na przykład, że `codeBlocks` jest to tablica <xref:microsoft.quantum.errorcorrection.logicalregister> wartości, które należy odzyskać.
> Następnie `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` zastosuje kod korygujący błędów `code` i funkcję odzyskiwania `recoveryFn` do każdego bloku niezależnie.
> Ta wartość jest przechowywana nawet dla klasycznych danych wejściowych: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` zastosuje obrót $ \pi/$2 o $X $, a po nim rotację $pi/$3 $Y $.

Q#Canon oferuje również obsługę klasycznych wzorców wyliczenia, które są znane do programowania funkcjonalnego.
Na przykład <xref:microsoft.quantum.arrays.fold> implementuje wzorzec $f (f (f (s \_ {\Text{Initial}}, x \_ 0), x \_ 1), \dots) $, aby zmniejszyć funkcję na liście.
Ten wzorzec może służyć do implementowania sum, produktów, wartości minimum, wartości maksymalnych i innych takich funkcji:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Podobnie funkcje takie jak <xref:microsoft.quantum.arrays.mapped> i <xref:microsoft.quantum.arrays.mappedbyindex> mogą służyć do wyrażania funkcjonalnych koncepcji programowania w programie Q# .

## <a name="composing-operations-and-functions"></a>Tworzenie operacji i funkcji ##

Konstrukcje przepływu sterowania oferowane przez firmy Canon podejmują działania i pełnią funkcję jako dane wejściowe, dzięki czemu mogą być w stanie redagować kilka operacji lub działać w jednym możliwym do przeniesieniu.
Na przykład wzorzec $UVU ^ {\dagger} $ jest niezwykle powszechny w programowaniu Quantum, w taki sposób, że Canon udostępnia operację <xref:microsoft.quantum.canon.applywith> jako abstrakcję dla tego wzorca.
Takie streszczenie umożliwia również bardziej wydajne przestrzeganie obwodów, ponieważ `Controlled` działania na tej sekwencji nie `U(qubit); V(qubit); Adjoint U(qubit);` muszą działać na każdym z nich `U` .
Aby to zobaczyć, pozwól $c (U) $ to jednostka reprezentująca `Controlled U([control], target)` i niech $c (V) $ można zdefiniować w taki sam sposób.
Następnie dla dowolnego stanu $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (uvu ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes u ^ \dagger) \ket {1} \otimes \ket{\psi}.
\end{align} przez definicję `Controlled` .
Z drugiej strony \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes U) (c (V)) (\boldone \otimes u ^ \dagger) \ket {0} \otimes \ket{\psi}.
\end{align} się według liniowości, możemy dowiedzieć się, że możemy w ten sposób wziąć pod uwagę $U $ w ten sposób dla wszystkich stanów wejścia.
Oznacza to, że $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Ponieważ operacje kontrolne mogą być kosztowne ogólnie, przy użyciu kontrolowanych wariantów, takich jak `WithC` i, `WithCA` mogą pomóc w zmniejszeniu liczby funktory kontroli, które należy zastosować.

> [!NOTE]
> Jednym z nich jest konieczność refaktoryzacji $U $, dlatego nie wiemy, jak zastosować `Controlled` Funktor do `U` .
> `ApplyWithCA` w związku z tym ma słaby podpis, niż może być oczekiwany:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Podobnie program <xref:microsoft.quantum.canon.bound> tworzy operacje, które stosują sekwencję innych operacji z kolei.
Na przykład następujące są równoważne:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Łączenie ze wzorcami iteracji może być szczególnie przydatne:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Kompozycja uporządkowana według czasu ###

Nadal jesteśmy w stanie kontynuować kontrolę przepływu pod względem częściowej aplikacji i funkcji klasycznych, a także można modelować nawet dość zaawansowane koncepcje Quantum w zakresie klasycznej kontroli przepływu.
Ta wartość analogiczna jest precyzyjna przez rozpoznawanie, że operatory jednostkowe odpowiadają dokładnie na skutki uboczne operacji wywołujących, takie, że jakakolwiek dekompozycja operatorów jednostkowych w odniesieniu do innych operatorów jednostkowych odpowiada za konstruowanie konkretnej sekwencji wywołania dla klasycznej procedury, która emituje instrukcje do działania jako określone operatory jednostkowe.
W tym widoku `Bound` jest precyzyjnie reprezentacja produktu macierzy, ponieważ `Bound([A, B])(target)` jest równoważne `A(target); B(target);` , co z kolei jest sekwencją wywołującą odpowiadającą $ba $.

Bardziej zaawansowanym przykładem jest [rozwinięcie Trotter — Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Jak opisano w sekcji reprezentacja generatora dynamicznego [struktur danych](xref:microsoft.quantum.libraries.data-structures), rozszerzanie Trotter – Suzuki zapewnia szczególnie przydatny sposób wyrażania wartości wykładniczych macierzy.
Na przykład zastosowanie rozwinięcia z najniższym porządkiem daje dla wszystkich operatorów $A $ i $B $, które $A = A ^ \dagger $ i $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i t/n) \exp (i B t/n) \right) ^ n.
\end{align} colloquially, oznacza to, że możemy około rozwijać stan w $A + B $ przez alternatywny sposób, w $A $ i $B $.
Jeśli reprezentujemy ewolucję w $A $ przez operację `A : (Double, Qubit[]) => Unit` , która stosuje $e ^ {i t A} $, reprezentacja rozwinięcia Trotter – Suzuki pod kątem zmiany kolejności wywołań zostanie wyczyszczona.
W konkretnym czasie, w przypadku operacji, `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` takiej jak `A = U(0, _, _)` i `B = U(1, _, _)` , możemy zdefiniować nową operację reprezentującą całkowity `U` czas $t $ przez generowanie sekwencji formularza

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Teraz możemy przyczynić się do rozszerzenia Trotter – Suzuki *bez odwołania do Mechanics Quantum*.
Rozszerzanie jest efektywnie bardzo konkretnym wzorcem iteracji, które zostały poddane przez $ \eqref{EQ: Trotter-Suzuki-0} $.
Ten wzorzec iteracji jest implementowany przez <xref:microsoft.quantum.canon.decomposeintotimestepsca> :

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

Sygnatura jest `DecomposeIntoTimeStepsCA` zgodna ze wspólnym wzorcem w Q# , gdzie kolekcje, których kopie zapasowe mogą być tworzone przez tablice lub przez elementy obliczeniowe na bieżąco, są reprezentowane przez krotki, których pierwsze elementy są `Int` wartościami wskazujące ich długości.

## <a name="putting-it-together-controlling-operations"></a>Umieszczenie go razem: kontrolowanie operacji ##

Na koniec firma Canon kompiluje się w `Controlled` Funktor, dostarczając dodatkowe sposoby wykonywania operacji Quantum.
Jest to typowy, szczególnie w przypadku arytmetycznego przetwarzania, do warunkowych operacji na Stanach obliczeniowych innych niż $ \ket{0\cdots 0} $.
Korzystając z operacji sterowania i funkcji wprowadzonych powyżej, możemy uzyskać więcej ogólnych warunków Quantum w jednej instrukcji.
Przejdźmy do sposobu, w jaki <xref:microsoft.quantum.canon.controlledonbitstring> to robi (parametry typu San), a następnie Podzielmy pojedyncze elementy o jeden.
Najpierw należy określić operację, która w rzeczywistości wykonuje silną transwierzenie implementacji kontroli na podstawie dowolnego stanu.
Nie wywołamy tej operacji bezpośrednio, ale dodamy ją `_` do początku nazwy, aby wskazać, że jest to implementacja innej konstrukcji w innym miejscu.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Należy pamiętać, że przyjmujemy ciąg bitów, reprezentowany jako `Bool` Tablica, za pomocą którego można określić warunek, który chcemy zastosować do danej operacji `oracle` .
Ponieważ ta operacja rzeczywiście wykonuje aplikację bezpośrednio, musimy również przyjąć rejestry kontroli i celu, reprezentowane w tym miejscu jako `Qubit[]` .

Następnie należy zauważyć, że kontrolowanie stanu podstawy obliczeniowej $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ dla ciągu bitowego $ \vec{s} $ może być zrealizowane przez transformowanie $ \ket{\vec{s}} $ do $ \ket{0\cdots 0} $.
W szczególności $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.
Ponieważ $X ^ {\dagger} = X $, to oznacza to, że $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $.
W tym celu możemy zastosować $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} $, zastosować `Controlled oracle` i przekształcić z powrotem do $ \vec{s} $.
Ta konstrukcja jest precyzyjna `ApplyWith` , dlatego należy odpowiednio napisać treść nowej operacji:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

W tym miejscu użyto, <xref:microsoft.quantum.canon.applypaulifrombitstring> Aby zastosować $P $, częściowo stosując się do jego celu do użycia z `ApplyWith` .
Należy jednak pamiętać, że musimy przekształcić rejestr *kontrolki* na nasz żądany formularz, więc częściowo stosujemy wewnętrzną operację `(Controlled oracle)` na *obiekcie docelowym*.
Spowoduje to pozostawienie w `ApplyWith` nawiasie klamrowym rejestracji kontrolki z $P $, dokładnie tak, jak jest to konieczne.

W tym momencie możemy to zrobić, ale jest to w jakiś sposób niezadowalający, że nasza nowa operacja nie "działa", jak zastosowanie `Controlled` Funktor.
W tym celu możemy zdefiniować nasze nowe koncepcje przepływu sterowania, pisząc funkcję, która powoduje, że baza danych Oracle będzie kontrolowana i która zwraca nową operację.
W ten sposób nasza nowa funkcja wygląda i czuje bardzo podobne `Controlled` , co oznacza, że można łatwo definiować zaawansowane nowe konstrukcje przepływu sterowania przy użyciu Q# i firmy Canon razem:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
