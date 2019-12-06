---
title: 'Biblioteki Q # standardowe — struktury danych | Microsoft Docs'
description: 'Biblioteki Q # standardowe — struktury danych'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6eb47de84fdfbb9d35fdfc2988883f8e1cffa332
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864359"
---
# <a name="data-structures-and-modeling"></a>Struktury i modelowanie danych #

## <a name="classical-data-structures"></a>Klasyczne struktury danych ##

Wraz z typami zdefiniowanymi przez użytkownika do reprezentowania koncepcji Quantum, Canon oferuje również operacje, funkcje i typy do pracy z danymi klasycznymi używanymi w kontroli systemów Quantum.
Na przykład funkcja <xref:microsoft.quantum.arrays.reversed> pobiera tablicę jako dane wejściowe i zwraca tę samą tablicę w odwrotnej kolejności.
Można go następnie użyć w tablicy typu `Qubit[]`, aby uniknąć konieczności stosowania niepotrzebnych bram $ \operatorname{SWAP} $ podczas konwersji między reprezentacjami jednostek Quantum.
Podobnie znaleźliśmy w poprzedniej sekcji, że typy formularzy `(Int, Int -> T)` mogą być przydatne do reprezentowania losowych kolekcji dostępu, więc funkcja <xref:microsoft.quantum.arrays.lookupfunction> zapewnia wygodny sposób konstruowania takich typów z typów tablic.

### <a name="pairs"></a>Parowanie ###

Firma Canon obsługuje notację w stylu funkcjonalnym dla par, uzupełniając dostęp do krotek przez dekonstrukcja:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Tablice ###

Canon oferuje kilka funkcji manipulowania tablicami.
Te funkcje są typu sparametryzowanego i mogą być używane z tablicami dowolnego typu Q #.
Na przykład funkcja <xref:microsoft.quantum.arrays.reversed> zwraca nową tablicę, której elementy znajdują się w odwrotnej kolejności od ich wejścia.
Może to służyć do zmiany sposobu reprezentowania rejestru Quantum podczas wywoływania operacji:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Podobnie funkcja <xref:microsoft.quantum.arrays.subarray> może służyć do zmiany kolejności lub podzbiorów elementów tablicy:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

W połączeniu z kontrolką przepływu funkcje manipulowania tablicą, takie jak <xref:microsoft.quantum.arrays.zip>, mogą zapewnić zaawansowany sposób wyznaczania programów Quantum:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Firmy Oracle ##

W [ocenie fazy](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) i literaturze [wzmocnienia amplitudy](https://en.wikipedia.org/wiki/Amplitude_amplification) koncepcje Oracle często pojawiają się.
W tym miejscu termin Oracle odwołuje się do procedury podrzędnej Blackbox Quantum, która działa na zestawie qubits i zwraca odpowiedź jako fazę.
Ta podprocedura często może być traktowana jako dane wejściowe algorytmu Quantum, który akceptuje Oracle, oprócz innych parametrów, i stosuje szereg operacji Quantum i traktowanie wywołania tej podprocedury Quantum, tak jakby była bramą podstawową.
Oczywiście, aby faktycznie zaimplementować większy algorytm, należy podać konkretną dekompozycję Oracle do podstawowych bram, ale takie dekompozycja nie jest wymagana w celu zrozumienia algorytmu, który wywołuje Oracle.
W Q # to Abstrakcja jest reprezentowana przy użyciu tego, że operacje są wartościami pierwszej klasy, w taki sposób, że operacje mogą być przesyłane do implementacji algorytmów Quantum w sposób czarno-Box.
Ponadto typy zdefiniowane przez użytkownika są używane do etykietowania różnych reprezentacji Oracle w sposób bezpieczny dla typu, co utrudnia przypadkowe rozliczanie różnych rodzajów operacji na czarnym pudełku.

Takie firmy Oracle są wyświetlane w wielu różnych kontekstach, w tym w przykładach sławę, takich jak [Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) i algorytmy symulacji Quantum.
W tym miejscu koncentrujemy się na systemach Oracle wymaganych przez tylko dwie aplikacje: wzmocnienie amplitudy i szacowanie faz.
Najpierw będziemy omawiać wzmocnienie wzmocnienia amplitudy przed rozpoczęciem szacowania faz.

### <a name="amplitude-amplification-oracles"></a>Wzmocnienie amplitudy dla rozwiązań firmy Oracle ###

Algorytm wzmocnienia amplitudy ma na celu przeprowadzenie obrotu między stanem początkowym i końcowym przez zastosowanie sekwencji odbicia stanu.
Aby algorytm działał, musi on mieć specyfikację obu tych stanów.
Te specyfikacje są podane przez dwie firmy Oracle.
Te Oracle działają, dzieląc dane wejściowe na dwie spacje, "miejsce docelowe" i "początkowe" miejsce.
Firmy Oracle identyfikują takie miejsca, podobnie jak operatory Pauli identyfikują dwie spacje, stosując fazę $ \Pm $1 do tych miejsc.
Główną różnicą jest to, że te miejsca nie muszą zawierać pół miejsca w tej aplikacji.
Należy również zauważyć, że te dwa podobszary nie są zwykle wykluczane wzajemnie: istnieją wektory, które są elementami członkowskimi obu spacji.
Jeśli ta wartość nie była równa true, wzmocnienie amplitudy nie będzie miało żadnego efektu, dlatego musimy mieć początkowe miejsce, aby nie nakładać się na wartość docelową.

Należy zwrócić uwagę na pierwszą firmę Oracle, której potrzebujemy, aby wzmocnienie amplitudy miało $P\_$0, zdefiniowane jako mają następujące działania.  Dla wszystkich stanów $ \ket{x} $ w "początkowym" miejscu $P\_0 \ket{x} =-\ket{x} $ i dla wszystkich stanów $ \ket{y} $, które nie znajdują się w tym miejscu, $P\_0 \ket{y} = \ket{y} $.
Oracle, który oznacza miejsce docelowe, $P _1 $, ma dokładnie taki sam formularz.
Dla wszystkich stanów $ \ket{x} $ w miejscu docelowym (tj. dla wszystkich stanów, które mają być używane przez algorytm), $P _1 \ KET {x} =-\ket{x} $.
Podobnie dla wszystkich stanów $ \ket{y} $, które nie znajdują się w docelowym miejscu $P _1 \ KET {y} = \ket{y} $.
Te dwa odbicia są następnie łączone w celu utworzenia operatora, który ustawia pojedynczy krok wzmocnienia amplitudy, $Q =-P_0 P_1 $, gdzie całkowity znak minus jest istotny tylko do uwzględnienia w kontrolowanych aplikacjach.
Wzmocnienie amplitudy następnie przechodzi przez pobranie stanu początkowego $ \ket{\psi} $, który znajduje się w początkowym miejscu, a następnie wykonuje $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
Wykonywanie takich iteracji gwarantuje, że jeśli jeden zaczyna się od początkowego stanu, który nakłada się na $ \sin ^ 2 (\theta) $ z oznaczonym obszarem, po $m $ iteracje to nakładają się $ \sin ^ 2 ([2 mln + 1] \theta) $.
Zwykle chcemy wybrać $m $, aby być bezpłatnym parametrem, takim jak $ [2 mln + 1] \theta = \ pi/2 $; jednak takie sztywne wybory nie są uznawane za istotne dla niektórych form wzmocnienia amplitudy, takich jak wzmocnienie amplitudy stałych punktów.
Ten proces pozwala nam przygotować stan w oznaczonym miejscu przy użyciu mniej więcej zapytań do funkcji oznaczania i funkcji przygotowania stanu, niż jest to możliwe na ściśle klasycznym urządzeniu.
Dzieje się tak dlatego, że wzmocnienie amplitudy jest znaczącym blokiem konstrukcyjnym dla wielu aplikacji przetwarzania Quantum.

Aby zrozumieć, jak używać algorytmu, warto podać przykład, który zapewnia konstrukcję rozwiązań firmy Oracle.  Rozważ wykonanie algorytmu Grover dla wyszukiwania bazy danych w tym ustawieniu.
W wyszukiwaniu Grover celem jest przekształcenie stanu $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ w jeden z (potencjalnie) wiele oznaczonych Stanów.
Aby jeszcze bardziej uprościć, spójrzmy na przypadek, w którym jedynym oznaczonym stanem jest $ \ket{0}$.
Następnie mamy zaprojektować dwie firmy Oracle: jeden oznaczający początkowy stan $ \ket{+} ^ {\otimes n} $ ze znakiem minus i inną, który oznacza oznaczony stan $ \ket{0}$ znakiem minus.
Tę ostatnią bramę można zaimplementować przy użyciu następującej operacji procesu przy użyciu operacji przepływu sterowania w programie Canon:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Ta Oracle jest wtedy szczególnym przypadkiem <xref:microsoft.quantum.canon.rall1> operacji, która umożliwia obracanie przez dowolną fazę zamiast przypadku odbicia $ \phi = \pi $.
W tym przypadku `RAll1` jest podobny do <xref:microsoft.quantum.intrinsic.r1> operacji Preludium, w tym, że obraca się około $ \ket{11\cdots1} $ zamiast w stanie qubit $ \ket{1}$.

Oracle, który oznacza początkowe miejsce, może być skonstruowany w podobny sposób.
W pseudokodzie:

1. Zastosuj $H $ brama do każdego qubit.
2. Zastosuj $X $ brama do każdego qubit.
3. Zastosuj $n-$1 kontrolowane $Z $-Gate do $n ^ {\Text{th}} $ qubit.
4. Zastosuj $X $ brama do każdego qubit.
5. Zastosuj $H $ brama do każdego qubit.

Tym razem pokazujemy również, jak używać <xref:microsoft.quantum.canon.applywith> wraz z <xref:microsoft.quantum.canon.rall1>ą operacją omówioną powyżej:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Następnie możemy połączyć te dwa firmy Oracle, aby obrócić między dwoma stanami i deterministycznie przekształcić $ \ket{+} ^ {\otimes n} $ do $ \ket{0}$ przy użyciu szeregu warstw bramy Hadamard, która jest proporcjonalna do $ \sqrt{2 ^ n} $ (program IE $m \propto \sqrt{2 ^ n} $) zamiast niedeterministycznych warstw $2 ^ n $, które byłyby konieczne do niedyskryminacyjnego przygotowania stanu $ \ket{0}$ przez przygotowanie i pomiar stanu początkowego do momentu zaobserwowania wyniku $0 $.

### <a name="phase-estimation-oracles"></a>Fazy oceny rozwiązań firmy Oracle ###

W przypadku szacowania fazy firmy Oracle są nieco bardziej naturalne.
Celem szacowania fazy jest zaprojektowanie podprocedury, która może próbkować z eigenvalues macierzy jednostkowej.
Ta metoda jest niezbędna w symulacji Quantum, ponieważ w przypadku wielu fizycznych problemów związanych z analizą chemiczną i nauką materiału te eigenvalues zapewniają niedrogią kondycję systemów Quantum, która zapewnia nam cenne informacje o diagramach faz dynamika materiałów i odpowiedzi dla cząsteczek.
Każda wersja oszacowania fazy musi być jednostką wejściową.
Ten moduł jest zwykle opisywany przez jeden z dwóch typów rozwiązań firmy Oracle.

> [!TIP]
> Oba typy Oracle opisane poniżej zostały omówione w przykładach.
> Aby dowiedzieć się więcej o programie Oracle Query, zobacz przykład [ **PhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation).
> Aby dowiedzieć się więcej na temat zapytań dyskretnych, zobacz [przykład **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

Pierwszy typ firmy Oracle, który wywołuje zapytanie dyskretne Oracle i reprezentuje typ zdefiniowany przez użytkownika <xref:microsoft.quantum.oracles.discreteoracle>, po prostu obejmuje macierz jednostkową.
Jeśli $U $ jest jednostką, której eigenvalues chcemy oszacować, a firma Oracle dla $U $ jest po prostu dodatkiem do procedury podrzędnej, która implementuje $U $.
Na przykład może upłynąć $U $, aby było to Oracle $Q $ zdefiniowany powyżej na potrzeby szacowania amplitudy.
Eigenvalues tej macierzy można użyć do oszacowania nakładania się między Stanami początkowymi i docelowymi $ \sin ^ 2 (\theta) $, przy użyciu kwadratów z mniejszą ilością próbek niż w przypadku, w przeciwnym razie będzie potrzebna.
Dzięki temu aplikacja do oceny fazy jest uzyskiwana przy użyciu Grover Oracle $Q $ jako dane wejściowe szacowania amplitudy.
Inna typowa aplikacja, szeroko wykorzystywana w metrologii Quantum, obejmuje oszacowanie małego kąta obrotu.
Innymi słowy, chcemy oszacować $ \theta $ dla nieznanej bramy rotacji w formularzu $R _z (\theta) $.
W takich przypadkach podprocedura, z którą będziemy korzystać w celu poznania ustalonej wartości $ \theta $ dla bramy to $ $ \begin{align} U & = R_z (\theta) \\\\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\\\ 0 & e ^ {i \ teta/2} \end{bmatrix}.
\end{align} $ $

Drugim typem Oracle używanym w ocenie fazy jest ciągłe zapytanie Oracle reprezentowane przez typ <xref:microsoft.quantum.oracles.continuousoracle>.
Ciągłe zapytanie Oracle do oceny fazy przyjmuje postać $U (t) $, gdzie $t $ jest znaną w sposób klasyczny.
Jeśli możemy $U $ być stałą jednostką, a następnie ciągłe zapytanie Oracle przyjmuje formularz $U (t) = U ^ t $.
Pozwala to na badanie macierzy, takich jak $ \sqrt{U} $, które nie mogły zostać zaimplementowane bezpośrednio w modelu zapytań dyskretnych.

Ten typ Oracle jest cenny, gdy nie testujesz konkretnej jednostki, ale raczej chcesz poznać właściwości generatora jednostki.
Na przykład w dynamicznej symulacji Quantum celem jest opracowanie obwodów Quantum, które blisko przybliżą $U (t) = e ^ {-i H t} $ dla matrycy hermitian $H $ i ewolucyjny czas $t $.
Eigenvalues $U (t) $ są bezpośrednio powiązane z eigenvaluesem $H $.
Aby to sprawdzić, należy rozważyć eigenvector $H $: $H \ket{E} = E\ket {E} $, a następnie można łatwo sprawdzić od definicji serii potęgowej w macierzy wykładniczej, która $U (t) \ket{E} = e ^ {i\phi} \ KET {E} = e ^ {-iEt} \ket{E} $.
W ten sposób szacujemy eigenphase $U (t) $ daje eigenvalue $E $, przy założeniu, że eigenvector $ \ket{E} $ jest wejściem do algorytmu szacowania fazy.
Jednak w tym przypadku wartość $t $ może być wybierana według uznania użytkownika, ponieważ w przypadku wystarczającej niskiej wartości $t $ eigenvalue $E $ można jednoznacznie odwrócić przez $E =-\ Fi/t $.
Ponieważ metody symulacji Quantum zapewniają możliwość przeprowadzenia ewolucji ułamkowej, to przyznaje ona algorytmom szacowania fazy dodatkową swobodę podczas wykonywania zapytania dotyczącego jednostki, w odróżnieniu od tego, czy dyskretny model zapytań zezwala tylko na unitaries $U formularza ^ j $ do zastosowania w przypadku liczby całkowitej $j $ zapytanie ciągłe Oracle pozwala nam przybliżyć unitaries formularza $U ^ t $ dla dowolnej rzeczywistej wartości $t $.
Jest to ważne, aby przeprowadzić ściskanie wszystkich ostatnich uncji algorytmów szacowania wydajności, ponieważ pozwala to na wybór dokładnego eksperymentu, który zapewni najwięcej informacji na temat $E $; Metody oparte na dyskretnych zapytaniach muszą podejmować działania, wybierając najlepszą liczbę całkowitą zapytań w algorytmie.

W ramach konkretnego przykładu należy wziąć pod uwagę problem związany z oszacowaniem, a nie kąt obrotu bramy, ale częstotliwość przetwarzania w systemie Quantum.
Jednostką, która opisuje takie bioquantum Dynamics, jest $U (t) = R_z (2 \ Omega t) $ dla czasu ewolucji $t $ i nieznana częstotliwość $ \omega $.
W tym kontekście możemy symulować $U (t) $ dla dowolnego $t $ przy użyciu pojedynczej $R _z $ bramy i ponieważ nie trzeba ograniczać wypróbujemy tylko do zapytań dyskretnych do jednostki.
Taki ciągły model ma również właściwość, którą częstotliwości większe niż $2 \ Pi $ można poznać z procesów szacowania fazy, które używają ciągłych zapytań, ponieważ informacje o fazie, które w przeciwnym razie byłyby maskowane przez gałąź — kawałki funkcji logarytmu mogą być ujawnione w wyniku eksperymentów wykonanych dla nieproporcjonalnych wartości $t $.
W związku z tym w przypadku problemów, takich jak te modele ciągłego zapytania dla oceny fazy Oracle, nie tylko są odpowiednie, ale są również preferowane dla dyskretnego modelu zapytań.
Z tego powodu funkcja Q # ma funkcje dla obu rodzajów zapytań i pozostawia ją użytkownikowi w celu podjęcia decyzji o algorytmie szacowania fazy w celu dopasowania ich do potrzeb i typu dostępnego dla programu Oracle.

## <a name="dynamical-generator-modeling"></a>Modelowanie generatora dynamicznego ##

Generatory czasowe opisują sposób, w jaki Stany rozwijają się w czasie. Na przykład dynamika stanu Quantum $ \ket{\psi} $ podlega Schrödinger równaniu $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ z hermitian Matrix $H $, znanym jako hamiltonian, jako generator ruchu. Ze względu na początkowy stan $ \ket{\psi (0)} $ w czasie $t = $0, formalne rozwiązanie do tego równania w czasie $t $ może być, w zasadzie, Zapisano $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $, gdzie $U wykładniczy macierzy (t) = e ^ {-i H t} $ jest znany jako operator ewolucji czasu jednostkowego. Chociaż skupmy się na generatorach tego formularza w następujący sposób, podkreślamy, że koncepcja jest bardziej szeroka, na przykład w symulacji otwartych systemów Quantum lub do bardziej abstrakcyjnych równań różnicowych.

Głównym celem symulacji dynamicznego jest zaimplementowanie operatora ewolucji czasu dla niektórych stanów Quantum zakodowanych w qubits komputera Quantum.  W wielu przypadkach hamiltonian może być podzielony na sumę niektórych $d $ prostsze warunki

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

w przypadku, gdy poszczególne terminy są łatwe do wdrożenia na komputerze Quantum. Na przykład, jeśli $H _j $ jest Pauli $X _1X_2 operator, który działa na 1. i 2 elementów rejestru qubit `qubits`, ewolucj czasowo dla każdej chwili $t $ można zaimplementować po prostu, wywołując operację `Exp([PauliX,PauliX], t, qubits[1..2])`, która ma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`sygnatury. Jak opisano w dalszej części symulacji hamiltonian, jedno rozwiązanie ma na celu przybliżone ewolucję czasu przez $H $ z sekwencją prostszej operacji

$ $ \begin{align} U (t) & = \left (e ^ {iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $

gdzie liczba całkowita $r > $0 kontroluje błąd przybliżenia.

Biblioteka modelowania generatora dynamicznego zapewnia strukturę służącą do systematycznego kodowania skomplikowanych generatorów pod kątem łatwiejszych generatorów. Taki opis może zostać następnie przesłany do, powiedzmy, biblioteka symulacji w celu zaimplementowania ewolucji czasu przez wybrany przez Ciebie algorytm symulacji z wieloma szczegółami.

> [!TIP]
> Dynamiczna biblioteka generatora opisana poniżej znajduje się w przykładach. Aby zapoznać się z przykładem opartym na modelu Ising, zobacz [przykład **IsingGenerators** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators).
> Przykład na podstawie wodoru molekularnego można znaleźć w [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) i [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui) Samples.

### <a name="complete-description-of-a-generator"></a>Pełny opis generatora ###

Na najwyższym poziomie kompletny opis hamiltonian jest zawarty w `EvolutionGenerator` typie zdefiniowanym przez użytkownika, który ma dwa składniki.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

Typ zdefiniowany przez użytkownika `GeneratorSystem` to klasyczny opis hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

Pierwszy element `Int` krotki przechowuje liczbę warunków $d $ w hamiltonian, a drugi element `(Int -> GeneratorIndex)` jest funkcją, która mapuje indeks liczby całkowitej w wartości $\{0, 1,..., d-1\}$ do typu `GeneratorIndex` zdefiniowanego przez użytkownika, który jednoznacznie identyfikuje każdy termin pierwotny w hamiltonian. Należy pamiętać, że przez wyrażenie kolekcji warunków w hamiltonian jako funkcja, a nie `GeneratorIndex[]`tablicy, umożliwia to na bieżąco Obliczanie `GeneratorIndex`, która jest szczególnie przydatna w przypadku opisywania Hamiltonians z dużą liczbą warunków.

Bez względu na to, jakie terminy pierwotne zidentyfikowane przez `GeneratorIndex` są łatwe do symulowania. Na przykład warunki pierwotne mogą być operatorami Pauli, jak wspomniano powyżej, ale mogą również być Fermionic Annihilation i operatory tworzenia często używane w symulacji chemicznej Quantum. Tak samo `GeneratorIndex` jest bez znaczenia, ponieważ nie opisują sposobu ewolucji czasu przez termin, do którego mogą być implementowane jako obwód Quantum.

Jest to rozwiązywane przez określenie `EvolutionSet` typu zdefiniowanego przez użytkownika, który mapuje dowolny `GeneratorIndex`, rysowany z pewnego zestawu kanonicznego, do operatora jednostki, `EvolutionUnitary`, wyrażony jako obwód Quantum. `EvolutionSet` definiuje Konwencję o strukturze `GeneratorIndex`, a także definiuje zestaw możliwych `GeneratorIndex`.

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Generatory operatorów Pauli ###

Konkretny i przydatny przykład generatorów to Hamiltonians, które są sumą operatorów Pauli, z których każdy może mieć inny współczynnik.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $, gdzie każdy $ \hat H_j $ jest teraz rysowany z grupy Pauli. W przypadku takich systemów udostępniamy `PauliEvolutionSet()` typu `EvolutionSet`, który definiuje Konwencję dotyczącą sposobu, w jaki element grupy Pauli i współczynnika mogą być identyfikowane przez `GeneratorIndex`, który ma następujący podpis.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

W naszym kodowaniu pierwszy parametr `Int[]` określa ciąg Pauli, gdzie $ \hat I\rightarrow $0, $ \hat X\rightarrow $1, $ \hat Y\rightarrow $2 i $ \hat Z\rightarrow $3. Drugi parametr `Double[]` przechowuje współczynnik ciągu Pauli w hamiltonian. Należy zauważyć, że używany jest tylko pierwszy element tej tablicy. Trzeci parametr `Int[]` indeksuje qubits, w którym działa ten ciąg Pauli i nie może zawierać zduplikowanych elementów. W tym celu hamiltonian termin $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ może być reprezentowany jako

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()` to funkcja, która mapuje dowolny `GeneratorIndex` tego formularza na `EvolutionUnitary` z następującą sygnaturą.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

Pierwszy parametr reprezentuje czas trwania, który zostanie pomnożony przez współczynnik w `GeneratorIndex`w przypadku ewolucji jednostkowej. Drugi parametr to qubit, w którym są rejestrowane działania jednostkowe. 

### <a name="time-dependent-generators"></a>Generatory zależne od czasu ###

W wielu przypadkach są również zainteresowani generatorami zależnymi od czasu, które mogą wystąpić w równaniu Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $, gdzie Generator $ \hat H (t) $ jest teraz zależne od czasu. Rozszerzenie od niezależnych generatorów czasowych powyżej do tego przypadku jest proste. Zamiast naprawione `GeneratorSystem`, które opisują hamiltonian przez cały czas $t $, mamy natomiast `GeneratorSystemTimeDependent` typu zdefiniowanego przez użytkownika.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

Pierwszy parametr jest parametrem harmonogramu ciągłego $s \In [0, 1] $, a funkcje tego typu zwracają `GeneratorSystem` dla tego harmonogramu. Należy zauważyć, że parametr Schedule może być liniowo związany z parametrem czasu fizycznego, np. $s = t/T $, przez pewien łączny czas symulacji $T $. Ogólnie rzecz biorąc nie ma to potrzeby.

Podobnie kompletny opis tego generatora wymaga `EvolutionSet`, więc definiujemy `EvolutionSchedule` typ zdefiniowany przez użytkownika.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
