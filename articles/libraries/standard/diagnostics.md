---
title: 'Biblioteki Q # standardowe — Diagnostyka | Microsoft Docs'
description: 'Biblioteki Q # standardowe — Diagnostyka'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: b59f91b660281167eab182529b415b6d379e3d63
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184495"
---
# <a name="diagnostics"></a>Diagnostyka #

Podobnie jak w przypadku klasycznego programowania, ważne jest, aby umożliwić Diagnozowanie błędów i błędów w programach Quantum.
Biblioteki Q # Standard zapewniają różne sposoby zapewniania poprawności programów Quantum, jak opisano w <xref:microsoft.quantum.techniques.testing-and-debugging>.
W dużym stopniu obsługa ta jest dostępna w formie funkcji i operacji, które powodują, że komputer docelowy dostarcza dodatkowe informacje diagnostyczne do programu hosta lub dewelopera lub wymusza prawidłowość warunków i nielicznych wyrażonych przez wywołanie funkcji lub operacji.

## <a name="machine-diagnostics"></a>Diagnostyka maszyny ##

Diagnostyka dotycząca klasycznych wartości można uzyskać za pomocą funkcji <xref:microsoft.quantum.intrinsic.message>, aby rejestrować komunikat w sposób zależny od maszyny.
Domyślnie program zapisuje ciąg w konsoli programu.
Używane razem z interpolowanymi ciągami, <xref:microsoft.quantum.intrinsic.message> ułatwia raportowanie informacji diagnostycznych o klasycznych wartościach:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` ma `(String -> Unit)`sygnatury, a tym samym nie można zaobserwować emitowania komunikatu dziennika debugowania z poziomu Q #.

<xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>, które są wywoływane, instruują komputery docelowe, aby dostarczać informacje diagnostyczne dotyczące wszystkich aktualnie przyznanych qubits lub odpowiednio określonego rejestru qubits.
Każdy komputer docelowy różni się w zależności od informacji diagnostycznych w odpowiedzi na instrukcję zrzutu.
Maszyna docelowa [pełnego stanu symulatora](xref:microsoft.quantum.machines.full-state-simulator) , na przykład, udostępnia program hosta z wektorem stanu, którego używa wewnętrznie do reprezentowania rejestru qubits.
Porównując, komputer docelowy [symulatora Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) zapewnia jeden klasyczny bit dla każdego qubitu.

 Aby dowiedzieć się więcej na temat danych wyjściowych [pełnego `DumpMachine` symulatora stanu](xref:microsoft.quantum.machines.full-state-simulator) , zapoznaj się z sekcją funkcje zrzutu w naszym artykule dotyczącym [testowania i debugowania](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Fakty i potwierdzenia ##

Jak opisano w [testowaniu i debugowaniu](xref:microsoft.quantum.techniques.testing-and-debugging), funkcja lub operacja z podpisem `Unit -> Unit` lub `Unit => Unit`, może być wywoływana jako *test jednostkowy*.
Każdy test jednostkowy zwykle składa się z małego programu Quantum oraz co najmniej jednego warunku, który sprawdza poprawność tego programu.
Warunki te mogą mieć postać _faktów_, które sprawdzają wartości danych wejściowych lub _zatwierdzeń_, które sprawdzają Stany jednego lub więcej qubitsów, które zostały przesłane jako dane wejściowe.

Na przykład `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` reprezentuje fakt matematyczny, że $1 + 1 = $2, natomiast `AssertQubit(One, qubit)` reprezentuje warunek, który pomiar `qubit` zwróci `One` z pewnością.
W poprzednim przypadku można sprawdzić poprawność warunku, używając tylko jego wartości, a w tym drugim musimy wiedzieć coś o stanie qubit, aby oszacować potwierdzenie.

Biblioteki Q # Standard zapewniają kilka różnych funkcji służących do reprezentowania faktów, w tym:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfact>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Testowanie Stanów qubit ###

W praktyce potwierdzenia opierają się na faktach, że klasyczne symulacje Quantum Mechanics nie muszą przestrzegać [theorem bez klonowania](https://arxiv.org/abs/quant-ph/9607018), tak że firma Microsoft może wprowadzać niefizyczne pomiary i potwierdzenia przy użyciu symulatora dla naszej maszyny docelowej.
W ten sposób można testować poszczególne operacje w klasycznym symulatorze przed wdrożeniem na sprzęcie.
Na komputerach docelowych, które nie dopuszczają oceny potwierdzeń, wywołania <xref:microsoft.quantum.intrinsic.assert> można bezpiecznie zignorować.

Bardziej ogólnie rzecz biorąc <xref:microsoft.quantum.intrinsic.assert>, qubits operacje, które mierzą, że pomiar pożądanych Pauli, będzie zawsze miał wynik.
Jeśli potwierdzenie nie powiedzie się, wykonywanie kończy się przez wywołanie `fail` z podaną wiadomością.
Domyślnie ta operacja nie jest zaimplementowana. symulatory, które mogą ją obsługiwać, powinny dostarczyć implementację, która przeprowadza sprawdzanie środowiska uruchomieniowego.
`Assert` ma `((Pauli[], Qubit[], Result, String) -> ())`sygnatury.
Ponieważ `Assert` jest funkcją z pustą krotką jako typem danych wyjściowych, nie ma żadnego wpływu na wywołania `Assert` są zauważalne w ramach programu Q #.

Wyniki operacji <xref:microsoft.quantum.intrinsic.assertprob>, które mierzą, że pomiar danego qubits w danej Pauli, będą mieć wynik z określonym prawdopodobieństwem, w ramach pewnej tolerancji.
Tolerancja jest dodatkiem (np. `abs(expected-actual) < tol`).
Jeśli potwierdzenie nie powiedzie się, wykonywanie kończy się przez wywołanie `fail` z podaną wiadomością.
Domyślnie ta operacja nie jest zaimplementowana. symulatory, które mogą ją obsługiwać, powinny dostarczyć implementację, która przeprowadza sprawdzanie środowiska uruchomieniowego.
`AssertProb` ma `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`sygnatury. Pierwszy z `Double` parametrów daje odpowiednie prawdopodobieństwo wyniku, a druga na tolerancję.

Możemy wykonać więcej niż potwierdzenie pojedynczej miary przy użyciu, że klasyczne informacje używane przez symulator do reprezentowania wewnętrznego stanu qubit są możliwe do skopiowania, dzięki czemu nie ma potrzeby faktycznego przeprowadzenia pomiaru w celu przetestowania naszej potwierdzenia.
W szczególności pozwala nam przyczynić się do *niezgodności* pomiarów, które byłyby niemożliwe na rzeczywistym sprzęcie.

Załóżmy, że `P : Qubit => Unit` jest operacją zaplanowaną do przygotowania stanu $ \ket{\psi} $, gdy jego dane wejściowe są w stanie $ \ket{0}$.
Niech $ \ket{\psi "} $ jest bieżącym stanem przygotowanym przez `P`.
Następnie $ \ket{\psi} = \ket{\psi '} $ If i tylko wtedy, gdy pomiar $ \ket{\psi '} $ na osi opisanej przez $ \ket{\psi} $ zawsze zwraca `Zero`.
Oznacza to, że \begin{align} \ket{\psi} = \ket{\psi '} \Text{if i tylko wtedy, gdy} \braket{\psi | \psi '} = 1.
\end{align} przy użyciu operacji pierwotnych zdefiniowanych w Preludium, możemy bezpośrednio wykonać pomiary, która zwraca `Zero`, jeśli $ \ket{\psi} $ jest eigenstate jednego z operatorów Pauli.


<xref:microsoft.quantum.diagnostics.assertqubit> operacji zapewnia szczególnie przydatne skróty, aby to zrobić w przypadku, gdy chcemy przetestować potwierdzenie $ \ket{\psi} = \ket{0}$.
Jest to typowe, na przykład, gdy firma Microsoft nie przeliczyła, aby zwracała Ancilla qubits do $ \ket{0}$ przed ich zwolnieniem.
Potwierdzenie dla $ \ket{0}$ jest również przydatne, gdy chcemy zastanowić się, że dwa `P` przygotowania stanu i operacje `Q` zarówno przygotują ten sam stan, jak i w przypadku, gdy `Q` obsługuje `Adjoint`.
W szczególności,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Zwykle jednak firma Microsoft może nie mieć dostępu do potwierdzeń o stanach, które nie pokrywają się z eigenstates operatorów Pauli.
Na przykład $ \ket{\psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ nie jest eigenstate żadnego operatora Pauli, tak że nie można użyć <xref:microsoft.quantum.intrinsic.assertprob>, aby jednoznacznie określić, że stan $ \ket{\psi '} $ jest równy $ \ket{\psi} $.
Zamiast tego musimy rozłożyć potwierdzenie $ \ket{\psi '} = \ket{\psi} $ do założeń, które mogą być testowane bezpośrednio przy użyciu elementów podstawowych obsługiwanych przez nasz symulator.
W tym celu pozwól $ \ket{\psi} = \Alpha \ket{0} + \beta \ket{1}$ dla liczb zespolonych $ \Alpha = a\_r + a\_i i i $ \beta $.
Należy zauważyć, że to wyrażenie wymaga czterech liczb rzeczywistych $\{\_r, a\_i, b\_r, b\_i\}$ do określenia, ponieważ każda liczba zespolona może być wyrażona jako suma części rzeczywistej i urojonej.
Ze względu na globalną fazę można jednak wybrać $a\_i = $0, aby w unikatowy sposób określić tylko trzy rzeczywiste liczby.

W tym celu należy określić trzy potwierdzenia, które są niezależne od siebie, aby potwierdzić oczekiwany stan.
Możemy to zrobić przez znalezienie prawdopodobieństwa przestrzegania `Zero` dla każdej miary Pauli, podaną $ \Alpha $ i $ \beta $, i potwierdzeń każdego niezależnie.
Pozwól $x $, $y $ i $z $ `Result` wartości dla Pauli $X $, $Y $ i $Z $ pomiarów.
Następnie przy użyciu funkcji prawdopodobieństwo dla pomiarów Quantum, \begin{align} \Pr (x = \texttt{Zero} | \Alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_\\\\ \Pr (y = \texttt{Zero} | \Alpha , \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \Alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).
\end{align}

Operacja <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementuje te potwierdzenia w formie wartości $ \Alpha $ i $ \beta $ jako wartościami typu <xref:microsoft.quantum.math.complex>.
Jest to przydatne, gdy oczekiwany stan można obliczyć matematycznie.

### <a name="asserting-equality-of-quantum-operations"></a>Potwierdzanie równości operacji Quantum ###

Z tego względu firma Microsoft miała już do końca operacje testowania, które są przeznaczone do przygotowania określonych stanów.
Często jednak interesuje, jak operacja działa w przypadku dowolnych danych wejściowych, a nie dla pojedynczego stałego wejścia.
Załóżmy na przykład, że zaimplementowano operację `U : ((Double, Qubit[]) => () : Adjoint)` odpowiadającą rodzinie operatorów jednostkowych $U (t) $ i posiadają jawny blok `adjoint` zamiast korzystać z `adjoint auto`.
Firma Microsoft może chcieć zainteresować, że $U ^ \dagger (t) = U (-t) $, zgodnie z oczekiwaniami, jeśli $t $ reprezentuje czas ewolucji.

Ogólnie mówiąc, istnieją dwie różne strategie, które możemy wykonać w celu potwierdzenia, że dwie operacje `U` i `V` działają identycznie.
Po pierwsze możemy sprawdzić, czy `U(target); (Adjoint V)(target);` zachowuje wszystkie Stany.
Po drugie możemy sprawdzić, czy `U(target); (Adjoint V)(target);` działające w połowie stanu Entangled zagwarantuje, że Entanglement.
Te strategie są implementowane przez operacje firmy Canon odpowiednio <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> i <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>.

> [!NOTE]
> Wymienione powyżej potwierdzenie zostało omówione w oparciu o [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), matematyczną strukturę, która odnosi się do operacji na $n $ qubits do Entangled Stanów na $2n $ qubits.
> W szczególności operacja Identity na $n $ qubits jest reprezentowana przez $n $ kopie Entangled stanu $ \ket{\beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$.
> Operacja <xref:microsoft.quantum.preparation.preparechoistate> implementuje ten isomorphism, przygotowując stan, który reprezentuje daną operację.

W przybliżeniu te strategie są rozróżniane w zależności od czasu.
Iteracja przez każdy stan wejściowy zabiera dodatkowy czas, podczas gdy użycie Entanglement jako odniesienia wymaga przechowywania dodatkowych qubits.
W przypadkach, gdy operacja implementuje operację typu "odwracalne", tak że firma Microsoft interesuje się tylko w przypadku Stanów bazowych obliczeniowych, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testy równości w tym ograniczonym zestawie danych wejściowych.

> [!TIP]
> Iteracja dla Stanów danych wejściowych jest obsługiwana przez operacje wyliczania <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> i <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Te operacje są bardziej ogólnie przydatne w przypadku stosowania operacji do każdego elementu kartezjańskiego produktu między dwoma lub więcej zestawami.

Jednak te dwa podejścia przetestują różne właściwości operacji pod kontrolą.
Ponieważ potwierdzenie w miejscu wywołuje każdą operację wiele razy, raz dla każdego stanu danych wejściowych, wszystkie losowe wybory i wyniki pomiarów mogą ulec zmianie między wywołaniami.
Z drugiej strony potwierdzenie odwołania wywołuje każdą operację dokładnie raz, aby sprawdzać, czy operacje są równe *pojedynczego zrzutu*.
Oba te testy są przydatne w celu zapewnienia poprawności programów Quantum.


## <a name="further-reading"></a>Dalsze odczytywanie ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
