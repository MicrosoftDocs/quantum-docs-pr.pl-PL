---
title: Scharakteryzowanie i statystyka Quantum
description: Dowiedz się, jak dane statystyczne pomiarów z szacowania fazy są używane do szacowania wartości wyników w programowaniu Quantum.
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: b226f355771f2b65399ebe00cc3de9429a3cebb0
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759913"
---
# <a name="quantum-characterization-and-statistics"></a>Scharakteryzowanie i statystyka Quantum #

Niezwykle ważne jest, aby mieć możliwość scharakteryzowania skutków operacji w celu opracowania przydatnych algorytmów Quantum.
Jest to trudne, ponieważ każde pomiary systemu Quantum daje maksymalnie jeden bit informacji.
Aby uzyskać informacje o eigenvalue, powiadom sam stan Quantum, wyniki wielu pomiarów muszą być połączone, aby użytkownik mógł zgłębiać wiele informacji potrzebnych do reprezentowania tych koncepcji.
Stany Quantum są szczególnie uciążliwych z powodu braku [klonowania theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) , że nie ma możliwości poznania dowolnego stanu Quantum z pojedynczej kopii stanu, ponieważ dzięki temu można tworzyć kopie stanu.
Ta zaciemnianie stanu Quantum od użytkownika jest odzwierciedlane w rzeczywistości, która Q# nie ujawnia ani nie definiuje stanu dla programów Quantum. *is*
W ten sposób zbliżamy się do charakterystyki Quantum przez traktowanie operacji i Stanów jako czarnych. Ta metoda jest często wspólna w przypadku eksperymentalnej praktycznej charakterystyki Quantum, weryfikacji i weryfikacji (QCVV).

Scharakteryzowanie różni się od wielu innych omawianych wcześniej bibliotek.
Celem tej funkcji jest mniej, aby poznać klasyczne informacje o systemie, a nie przekształcenie jednostkowe na wektor stanu.
W związku z tym te biblioteki muszą mieszać zarówno klasyczne, jak i Quantum przetwarzanie informacji.


## <a name="iterative-phase-estimation"></a>Szacowanie fazy iteracji ##

Wyświetlanie programowania Quantum w kontekście określania klasy Quantum sugeruje przydatną alternatywę dla szacowania fazy Quantum.
Oznacza to, że zamiast przygotował $n $-qubit Register, aby zawierał binarną reprezentację fazy w ramach szacowania fazy Quantum, możemy wyświetlić oszacowanie fazy jako proces, za pomocą którego Agent *klasyczny* uczy właściwości systemu Quantum poprzez pomiary.
Przejdziemy tak jak w przypadku Quantum w przypadku użycia fazy Kickback, aby przekształcić aplikacje dla operacji czarno o nieznanym kącie, ale będzie to miara Ancilla qubit, które obracamy się w każdym kroku bezpośrednio po rotacji.
Jest to zalety, że wymaga tylko pojedynczej dodatkowej qubit do wykonania fazy KickBack opisanej w przypadku Quantum, ponieważ następnie uczymy fazę od wyników pomiaru w każdym kroku w sposób iteracyjny.  
Każda z metod proponowanych poniżej używa innej strategii do projektowania eksperymentów i różnych metod przetwarzania danych w celu uzyskania informacji o fazie.  Każdy z nich ma unikatową korzyść w zakresie od uzyskania rygorystycznych powiązań błędów, do możliwości uwzględniania wcześniejszych informacji, tolerowania błędów lub uruchamiania w pamięci limitted klasyczne komputery.

W omawianiu oszacowania fazy iteracyjnej będziemy rozważać $U jednostkowe $ podaną jako operację czerni.
Zgodnie z opisem w sekcji dotyczącej rozwiązań firmy Oracle w [strukturach danych](xref:microsoft.quantum.libraries.data-structures)firmy Q# Canon modeluje takie operacje według <xref:microsoft.quantum.oracles.discreteoracle> typu zdefiniowanego przez użytkownika, zdefiniowanego przez typ krotki `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
W konkretnym przypadku, `U : DiscreteOracle` a następnie `U(m)` implementuje $U ^ m $ dla `m : Int` .

W przypadku tej definicji, każdy krok iteracji fazy szacowania kontynuuje proces przygotowywania pomocniczej qubit w stanie $ \ket{+} $ wraz z początkowym stanem $ \ket{\phi} $ przyjętym przez nas jest [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) $U (m) $, tj. $U (m) \ket{\phi} = e ^ {im\phi} \ KET {\ Fi} $.  
`U(m)`Następnie zostanie użyta aplikacja, która przygotuje stan $ \left (R \_ 1 (m \phi) \ket{+} \right) \ket{\phi} $.
Podobnie jak w przypadku Quantum, wpływ kontrolowanej aplikacji Oracle `U(m)` jest dokładnie taki sam, jak efekt zastosowania $R _1 $ dla nieznanej fazy w $ \ket{+} $, dzięki czemu możemy opisać efekty $U $ w ten sposób prostsze.
Opcjonalnie algorytm obraca qubit kontrolki, stosując $R _1 (-m\theta) $, aby uzyskać stan $ \ket{\psi} = \left (R \_ 1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
Pomocnicza qubit używana jako kontrolka `U(m)` jest następnie mierzona na podstawie $X $ w celu uzyskania jednego klasycznego `Result` .

W tym momencie Rekonstruowanie fazy z `Result` wartości uzyskanych za pomocą szacowania fazy iteracyjnej jest klasycznym problemem statystycznym wnioskowania.
Znalezienie wartości $m $, która maksymalizuje zdobyte informacje, z uwzględnieniem ustalonej metody wnioskowania, jest po prostu problemem w statystyce.
Podkreślamy to, krótko opisując ocenę fazy iteracyjnej na poziomie teoretycznym w formalnym zakresie szacowania parametrów bayesowskie przed przystąpieniem do opisywania algorytmu statystycznego dostępnego w firmie Q# Canon do rozwiązywania tego problemu.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Szacowanie fazy iteracyjnej bez Eigenstates ###

Jeśli podany jest stan wejściowy, który nie jest eigenstate, co oznacza, że jeśli $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $, wówczas proces szacowania fazy nie jest w sposób jednoznaczny zorientowany na pojedynczy eigenstate energetyczny.  Eigenstate, do którego ostatecznie jest zbieżny, jest eigenstate, który najprawdopodobniej wyprodukował obserwowane `Result` .

W odniesieniu do jednego kroku środowiska uruchomieniowego jest wykonywana następująca niezależna transformacja na stanie \begin{align} \ sum_j \sqrt{\Pr (\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\phi \_ j)} \sqrt{\Pr (\Text{Result} | \phi \_ j)} \Ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \sum \_ j \Pr (\Text{Result} | \phi \_ j)}}.
\end{align}, ponieważ ten proces jest powtarzany przez wiele `Result` wartości, eigenstates, które nie mają maksymalnych wartości $ \ prod_k \pr (\Text{Result} \_ k | \phi \_ j) $ zostanie pominięty wykładniczo.
W efekcie proces wnioskowania będzie przerastał zbieżność do Stanów o pojedynczej eigenvalue, jeśli eksperymenty są wybrane prawidłowo.

Bayesa ' theorem dodatkowo sugeruje, że stan, który wynika z oszacowania fazy, jest zapisywana w postaci \begin{align} \frac{\sqrt{\Pr (\phi \_ j)} \sqrt{\Pr (\Text{Result} | \phi \_ j)} \ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \Sum \_ j \Pr (\Text{Result} | \phi \_ j)}} = \ sum_j \sqrt{\Pr (\phi \_ j | \Text{Result})} \ket{\phi \_ j}.
\end{align} tutaj $ \Pr (\phi \_ j | \Text{Result}) $ może być interpretted jako prawdopodobieństwo, że jeden z nich będzie miał wartość ascribe do każdej hipotezy dotyczącej danego eigenstatesu:

1. znajomość stanu Quantum przed pomiarem,
2. znajomość eigenstatesów $U $ i,
3. znajomość eigenvaluesów $U $.

Uczenie tych trzech rzeczy jest często wykładnicze na klasycznym komputerze.
Narzędzie do szacowania faz ma wpływ na to, że nie jest to niewielki zakres, od faktu, że może wykonywać takie zadanie uczenia Quantum bez znajomości jakichkolwiek z nich.
Oszacowanie fazy z tego powodu występuje w wielu algorytmach Quantum, które udostępniają wykładniczą przyspieszenia.

### <a name="bayesian-phase-estimation"></a>Oszacowanie fazy bayesowskie ###

> [!TIP]
> Aby uzyskać więcej informacji na temat szacowania fazy bayesowskie w sposób, zobacz przykład [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) .

Koncepcja szacowania fazy bayesowskie jest prosta.
Dane statystyczne pomiarów można zbierać z poziomu protokołu szacowania fazy, a następnie przetwarzać wyniki przy użyciu wnioskowania bayesowskie i podać oszacowanie parametru.
To przetwarzanie zapewnia oszacowanie eigenvalue oraz niepewność w tym szacunku.
Umożliwia również przeprowadzanie eksperymentów adaptacyjnych i korzystanie z wcześniejszych informacji.
Reguła "wadą" metod jest, że jest to wymaganie obliczeniowe.

Aby zrozumieć, jak działa ten proces wnioskowania bayesowskie, rozważ przypadek przetwarzania pojedynczego `Zero` wyniku.
Należy pamiętać, że $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, tak że $ \ket{+} $ jest jedyną dodatnią eigenstateem $X $ odpowiadającym `Zero` .
Prawdopodobieństwo zaobserwowania `Zero` dla [ `PauliX` pomiaru](xref:microsoft.quantum.concepts.pauli) na pierwszym qubitu ze stanem wejściowym $ \ket{\psi}\ket{\phi} $ to w ten sposób \begin{Equation} \Pr (\texttt{zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} w przypadku iteracji fazy iteracyjnej mamy, że $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, takich jak \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: faza-Est — prawdopodobieństwo}.
\end{align} to jest, iteracyjne szacowanie faz polega na uczeniu częstotliwości drgań funkcji sinusoidalną, pod kątem możliwości odwrócenia monety z odchyleniami podaną przez sinusoid.
Zgodnie z tradycyjną klasyczną terminologią, wywołamy metodę $ \eqref{EQ: Phase-Est — prawdopodobieństwo} $ *Funkcja prawdopodobieństwa* dla szacowania fazy iteracji.

Po zaobserwowanym `Result` z funkcji prawdopodobieństwo oszacowania fazy iteracji możemy użyć reguły Bayesa ', aby określić, co powinna być uważana za tę obserwację.
W konkretnym miejscu \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation} WHERE $d \In \\ {\texttt{zero}, \texttt{one} \\ } $ to a `Result` , gdzie $ \Pr (\phi) $ opisuje poprzednią przekonania o $ \phi $.
Powoduje to, że iteracyjny charakter iteracyjnej oceny fazy jest jawny, jako rozkład tylny $ \Pr (\phi | d) $ opisuje nasze przekonania bezpośrednio przed naszymi obserwacją następnego `Result` .

W dowolnym momencie podczas tej procedury możemy raportować fazę $ \hat{\phi} $ wnioskowaną przez klasyczny kontroler jako \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \Text{data}] = \int \phi \Pr (\phi | \Text{Data}) {\mathrm d} \phi, \end{Equation}, gdzie $ \Text{Data} $ oznacza cały otrzymany rekord wszystkich `Result` uzyskanych wartości.

Dokładne wnioskowanie bayesowskie jest w sposób nieodpowiedniy do przeprowadzenia.
Aby wyświetlić ten obraz, chcielibyśmy poznać zmienną $n $-bitową $x $.
Wcześniejsza dystrybucja $ \Pr (x) $ ma obsługę ponad $2 ^ n $ hipotetycznych wartości $x $.
Oznacza to, że jeśli potrzebujemy wysoce dokładnego oszacowania $x $, szacowanie fazy bayesowskie może wymagać zabraniania pamięci i czasu przetwarzania.
Chociaż w przypadku niektórych aplikacji, takich jak symulacja Quantum, wymagana dokładność limitted nie wyklucza takich metod inne aplikacje, takie jak skró, nie można użyć dokładnej bayesowskie wnioskowania w ramach etapu szacowania fazy.  Z tego powodu udostępniamy również implementacje przybliżonych metod bayesowskie, takich jak [szacowanie etapowych przeszukiwań (RWPE)](xref:microsoft.quantum.research.characterization.randomwalkphaseestimation) , a także inne podejścia niebayesowskieowe, takie jak [niezawodna Ocena faz](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Niezawodna Ocena fazy ###

Maksymalna bayesowskie odbudowy fazy *szacowania z wyników* pomiarów jest wykładniczo trudna w najgorszym przypadku. W ten sposób większość praktycznych algorytmów szacowania fazy pogorszy pewną jakość w odbudowie, w programie Exchange dla ilości klasycznego przetwarzania końcowego, który zamiast tego skaluje się wielomianowo z liczbą wykonanych pomiarów.

Jednym z takich przykładów z wydajnym klasycznym etapem przetwarzania jest [niezawodny algorytm szacowania fazy](https://arxiv.org/abs/1502.02677), z jego sygnaturą i danymi wejściowymi wymienionymi powyżej. Przyjęto założenie, że wejściowe pola $U $ są opakowane jako `DiscreteOracle` Typ, i w związku z tym tylko wykonuje zapytania w postaci liczby całkowitej dla kontrolowanej $U $. Jeśli dane wejściowe w `Qubit[]` rejestrze to eigenstate $U \ket{\psi} = e ^ {i\phi} \ KET {\ psi} $, algorytm szacowania fazy niezawodnej zwraca oszacowanie $ \hat{\phi}\In [-\pi, \pi) $ z $ \phi $ jako `Double` .

Najważniejszym elementem niezawodnym oszacowania fazy, który jest współużytkowany z większością użytecznych wariantów, jest to, że jakość budowy klasy $ \hat{\phi} $ jest w pewnym sensie Heisenberg-Limited. Oznacza to, że jeśli odchylenie $ \hat{\phi} $ od prawdziwej wartości to $ \sigma $, a $ \sigma $ jest skalowane proporcjonalnie do całkowitej liczby zapytań $Q $ wykonane do kontroli $U $, tj. $ \sigma = \mathcal{O} (1/Q) $. Teraz definicja odchylenia różni się od różnych algorytmów szacowania. W niektórych przypadkach może to oznaczać, że w przypadku co najmniej $ \mathcal{O} (1) $ prawdopodobieństwa błąd szacowania $ | \hat{\phi}-\phi | \_ \circ\le \sigma $ dla pewnej miary cyklicznej $ \circ $. W przypadku niezawodnych ocen fazy, odchylenie jest dokładne od wariancji $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [(\mod \_ {2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $ Jeśli rozwinie okresowe fazy do jednego skończonego interwału $ (-\pi, \pi] $. Dokładniej, odchylenie standardowe w niezawodnej ocenie fazy jest zgodne ze znakiem nierówności $ $ \begin{align} 2,0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10,7 \ pi/Q, \end{align} $ $, gdzie Dolna granica jest osiągnięta w limicie asymptotically duży $Q $, a górna granica jest gwarantowana nawet dla małych rozmiarów próbek.  Należy pamiętać, że $n $ wybranych przez `bitsPrecision` dane wejściowe, które niejawnie definiuje $Q $.

Inne istotne szczegóły obejmują:, na przykład, obciążenie małą ilością tylko $1 $ Ancilla qubit lub że procedura jest nieadaptacyjna, co oznacza, że wymagana sekwencja eksperymentów Quantum jest niezależna od wyników pomiaru pośredniego. W tym i przemieszczonych przykładach, w których jest ważne, aby wybrać algorytm szacowania fazy, należy zapoznać się z dokumentacją, taką jak @"microsoft.quantum.characterization.robustphaseestimation" i publikacjami, do których istnieją odwołania, aby uzyskać więcej informacji i ich implementacji.

> [!TIP]
> Istnieje wiele przykładów, w których jest używane niezawodne szacowanie faz. W przypadku szacowania fazy w przypadku wyodrębnienia energii stanu ziemi w różnych systemach fizycznych należy zapoznać się z przykładem [ **symulacji H2** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line), [przykładem **SimpleIsing** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)i [przykładowym **modelem Hubbard** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Ciągłe firmy Oracle ###

Możemy również uogólnić z modelu Oracle użytego powyżej, aby umożliwić korzystanie z Oracle w czasie ciągłym, które są modelowane przez typ firmy <xref:microsoft.quantum.oracles.continuousoracle> .
Rozważmy, że zamiast pojedynczego operatora jednostkowego $U $, mamy rodzinę operatorów jednostkowych $U (t) $ for $t \In \mathbb{R} $, takich jak $U (t) U (s) $ = $U (t + s) $.
Jest to słaba instrukcja, niż w przypadku odrębnego przypadku, ponieważ możemy utworzyć element, <xref:microsoft.quantum.oracles.discreteoracle> ograniczając $t = m \, \delta t $ dla niektórych stałych $ \delta t $.
Według [theorem kamienia](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ dla pewnego operatora $H $, gdzie $ \exp $ to macierz wykładnicza, zgodnie z opisem w [zaawansowanych macierzach](xref:microsoft.quantum.concepts.matrix-advanced).
Eigenstate $ \ket{\phi} $ $H $, które $H \ket{\phi} = \phi \ket{\phi} $, również eigenstate of $U (t) $ dla wszystkich $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

Można zastosować dokładnie tę samą analizę omówioną w przypadku [szacowania fazy bayesowskie](#bayesian-phase-estimation) , a funkcja prawdopodobieństwo jest dokładnie taka sama dla tego bardziej ogólnego modelu Oracle: $ $ \Pr (\texttt{zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} {2} \right).
$ $ Ponadto, jeśli $U $ to symulacja dynamicznego generatora, tak jak w przypadku [symulacji hamiltonian](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), interpretujemy $ \phi $ jako energię.
W rezultacie użycie szacowania fazy z ciągłymi zapytaniami pozwala nam poznać symulowany [zakres energii dla cząsteczek](https://arxiv.org/abs/quant-ph/0604193), [materiałów](https://arxiv.org/abs/1510.03859) lub [pola teorie](https://arxiv.org/abs/1111.3633v2) , bez konieczności naruszania wybranych eksperymentów, wymagając $t $ jako liczby całkowitej.

### <a name="random-walk-phase-estimation"></a>Szacowanie fazy losowego przeszukiwania ###

Q# zapewnia przydatne przybliżenie oceny fazy bayesowskie przeznaczonej do użycia w pobliżu urządzeń Quantum, które działają przez Kondycjonowanie losowego przeszukiwania rekordów danych uzyskanych z oszacowania fazy iteracyjnej.
Ta metoda jest zarówno adaptacyjna, jak i całkowicie deterministyczna, co pozwala na niemal optymalne skalowanie błędów w szacowanej fazie $ \hat{\phi} $ z bardzo niewielką ilością pamięci.

Protokół używa przybliżonej metody wnioskowania bayesowskie, która zakłada, że wcześniejsza dystrybucja to gaussowskie.
To założenie gaussowskie pozwala nam używać formuły analitycznej dla eksperymentu, który minimalizuje wariancję tylną.
Następnie algorytm, w oparciu o wynik tego eksperymentu, przenosi wartość $ \phi $ left lub right w dół według wstępnie ustalonej wartości i zmniejsza wariancję według wstępnie ustalonej wartości.
Ta średnia i Wariancja zawierają wszystkie informacje, które są konieczne do określenia gaussowskie przed elementem $ \phi $ dla następnego eksperymentu.
Nieoczekiwane błędy pomiarowe lub rzeczywisty wynik na końcach początkowego poprzedzającego, może to spowodować niepowodzenie tej metody.
Odzyskuje się od awarii przez przeprowadzenie eksperymentów w celu sprawdzenia, czy bieżąca średnia i odchylenie standardowe są odpowiednie dla systemu.
Jeśli nie, wówczas algorytm wykonuje przechodzenie krok po kroku, a proces jest kontynuowany.
Możliwość przechodzenie do tyłu pozwala również algorytmowi dowiedzieć się, nawet jeśli początkowe odchylenie standardowe jest inapropriately małe.

## <a name="calling-phase-estimation-algorithms"></a>Algorytmy szacowania fazy wywołania ##

Każda operacja szacowania fazy dostarczana z użyciem firmy Q# Canon przyjmuje inny zestaw danych wejściowych parametryzacja jakość, której potrzebujemy z końcowego oszacowania $ \hat{\phi} $.
Te różne dane wejściowe, jednak wspólnie współdzielą kilka danych wejściowych, takie jak częściowa aplikacja przez parametry jakości, skutkuje typowym podpisem.
Na przykład <xref:microsoft.quantum.characterization.robustphaseestimation> operacja omówiona w następnej sekcji ma następujący podpis:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision`Dane wejściowe są unikatowe dla `RobustPhaseEstimation` , chociaż `oracle` i `eigenstate` są wspólne.
Tak więc, jak widać w **H2Sample**, operacja może akceptować algorytm iteracyjnej oceny fazy z wejściem formularza, `(DiscreteOracle, Qubit[]) => Unit` Aby zezwolić użytkownikowi na określenie dowolnych algorytmów szacowania fazy:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Te algorytmy szacowania fazy wyposażono są zoptymalizowane pod kątem różnych właściwości i parametrów wejściowych, które należy zrozumieć w celu zapewnienia najlepszego wyboru dla aplikacji docelowej. Na przykład niektóre algorytmy szacowania fazy są adaptacyjne, co oznacza, że przyszłe kroki są kontrolowane w sposób klasyczny przez wyniki pomiarów poprzednich kroków. Niektóre z nich wymagają możliwości exponentiate swojej wbudowanej sieci firmy Oracle z dowolnymi rzeczywistymi uprawnieniami, a inne wymagają tylko liczby całkowitej, ale mogą jedynie rozpoznać oszacowanie fazy modulo $2 \ pi $. Niektóre wymagają wielu pomocniczych qubits, a inne wymagają tylko jednego.

Podobnie użycie szacowania fazy losowego przeszukiwania przebiega w podobny sposób, jak w przypadku innych algorytmów udostępnianych w języku Canon:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
