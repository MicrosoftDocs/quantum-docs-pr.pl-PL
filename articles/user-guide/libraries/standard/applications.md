---
title: Aplikacje w bibliotekach standardowych Q
description: Dowiedz się więcej o dwóch podstawowych aplikacjach związanych z przetwarzaniem Quantum — hamiltonian symulacji i algorytmem wyszukiwania skró.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25b06ac697c958b15a756191fb8a4ac49644edd7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275797"
---
# <a name="applications"></a>Aplikacje #

## <a name="hamiltonian-simulation"></a>Symulacja Hamiltona ##

Symulacja systemów Quantum jest jednym z najbardziej atrakcyjnych zastosowań obliczeń Quantum.
Na klasycznym komputerze trudność symulowania Mechanics Quantum, ogólnie rzecz biorąc, Skaluje wymiar $N $ swojej reprezentacji wektora stanu.
Ponieważ ta reprezentacja rośnie wykładniczo z liczbą $n $ qubits $N = 2 ^ n $, cecha znana także jako [ponosi](xref:microsoft.quantum.concepts.multiple-qubits)się do naliczania wartości, Symulacja Quantum dla klasycznego sprzętu jest niezależna.

Jednak sytuacja może być bardzo różna w przypadku sprzętu Quantum. Najbardziej typowa zmiana symulacji Quantum jest nazywana niezależnym czasem problemem symulacji hamiltonian. Istnieje jednak jeden z opisów systemu, $H $, który jest matrycą hermitian, i pewien początkowy stan Quantum $ \ket{\psi (0)} $, który jest zakodowany w sposób niezależny od $n $ qubits na komputerze Quantum. Stany Quantum w systemach zamkniętych rozwijają się w ramach równania Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ celem jest zaimplementowanie operatora ewolucji czasu jednostkowego $U (t) = e ^ {-iHt} $ w niestałym czasie $t $, gdzie $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ rozwiązuje równanie Schrödinger.
Analogicznie, zależny od czasu problem symulacji hamiltonian rozwiązuje takie samo równanie, ale z $H (t) $ teraz funkcją czasu.

Symulacja hamiltonian jest głównym składnikiem wielu innych problemów z symulacją usługi Quantum, a rozwiązaniami związanymi z symulacją hamiltonian są algorytmy opisujące sekwencję pierwotnych bram Quantum, które umożliwiają wyznaczanie przybliżonych jednostek $ \tilde{U} $ z błędem $ \\ | \tilde{U}-U (t) \\ | \le \epsilon $ w [normie widmowej](xref:microsoft.quantum.concepts.matrix-advanced). Złożoność tych algorytmów jest bardzo silnie zależała od tego, w jaki sposób opis hamiltonian zainteresowania jest dostępny dla komputera Quantum. Na przykład w najgorszym przypadku, jeśli $H $ działające na $n $ qubits zostały podane jako lista $2 ^ n \times 2 ^ n $ Numbers, po jednym dla każdego elementu macierzy po prostu odczytywanie danych będzie wymagało wykładniczego czasu. W najlepszym przypadku jedna z nich może przyjąć dostęp do wielodostępnego modułu, który $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ w sposób nieprosty rozwiązuje problem. Żaden z tych modeli danych wejściowych nie jest szczególnie interesujący — nie jest to dawne podejście, które nie jest lepiej niż w przypadku klasycznych metod, a drugie, jak czarne pole ukrywa złożoność bramy pierwotnej, co może być wykładnicze w liczbie qubits.

### <a name="descriptions-of-hamiltonians"></a>Opisy Hamiltonians ###

W związku z tym wymagane są dodatkowe założenia formatu danych wejściowych. Należy zachować równowagę między modelami wejściowymi, które są wystarczająco opisowe, aby obejmowały interesujące Hamiltonians, takie jak te dla realistycznych systemów fizycznych lub interesujących problemów obliczeniowych, oraz modeli wejściowych, które są wystarczająco restrykcyjne w celu wydajnego zaimplementowania na komputerze Quantum. Różne nieuproszczone modele wejściowe mogą znajdować się w literaturze i mieszczą się w zakresie od Quantum do klasycznej. 

Jako przykłady modeli wejściowych Quantum, [oparta na przykładach symulacja Hamiltoniana](http://www.nature.com/articles/s41534-017-0013-7) zakłada dostęp do operacji Quantum, które tworzą kopie macierzy gęstości $ \rho $, które są przeznaczone do hamiltonian $H $. W [modelu dostępu](https://arxiv.org/abs/1202.5822) jednokierunkowego, Załóżmy, że hamiltonian w sumie unitaries $ $ \begin{align} H & = \sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j, \end{align} $ $, gdzie $a \_ j>$0 są współczynnikiem, a $ \hat{U} \_ j $ to unitaries. Następnie zakłada się, że jeden z nich ma dostęp z czerni do jednostki Oracle $V = \sum ^ {d-1} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} \_ j $, który wybiera żądany $ \hat{U} \_ j $, i Oracle $A \ket {0} = \sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ sum ^ {d-1} \_ {k = 0} \Alpha \_ j} \ket{j} $, które tworzą kodowanie stanu Quantum. W przypadku [symulacji hamiltonian rozrzedzonej](https://arxiv.org/abs/quant-ph/0301023), jedna zakłada, że hamiltonian jest macierzą rozrzedzoną, tylko $d = \mathcal{O} (\Text{polylog} (N)) $ niezerową elementu w każdym wierszu. Ponadto jeden z nich zakłada istnienie wydajnych obwodów Quantum, które wyprowadzają lokalizację tych elementów innych niż zero, a także ich wartości. Złożoność [algorytmów symulacji hamiltonian](xref:microsoft.quantum.more-information) jest oceniana w postaci liczby zapytań do tych czarnych pól, a złożoność bramy pierwotnej zależy znacznie od trudności związanych z wdrażaniem tych czerni.

> [!NOTE]
> Notacja Big-O jest często używana do opisywania stopnia złożoności algorytmów. Podaną dwie funkcje prawdziwe $f, g $, wyrażenie $g (x) = \mathcal{O} (f (x)) $ oznacza, że istnieje bezwzględna dodatnia stała $x \_ 0, c>$0, taka jak $g (x) \le c f (x) $ dla wszystkich $x \ge x \_ $0. 

W większości praktycznych aplikacji, które mają być implementowane na komputerze z systemem Quantum, te czarne pola muszą być efektywnie zaimplementowane, czyli z $ \mathcal{O} (\Text{polylog} (N)) $ pierwotnymi bramami Quantum. Bardziej silnie simulable Hamiltonians musi mieć wystarczająco rozrzedzony opis klasyczny. W jednym z takich rodzajów, zakłada się, że hamiltonian dekomponowa w sumie hermitian części $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $ Ponadto zakłada się, że każda część, hamiltonian $H \_ j $, jest łatwa do symulowania. Oznacza to, że jednostka $e ^ {-iH \_ j t} $ dla dowolnej godziny $t $ może być implementowana dokładnie przy użyciu $ \mathcal{O} (1) $ pierwotnych bram Quantum. Dotyczy to na przykład sytuacji, w której każda $H \_ j $ są lokalnymi operatorami Pauli, co oznacza, że są to produkty dwuczęściowe klasy $ \mathcal{O} (1) $ operatory nietożsamości Pauli, które działają w pobliżu blisko qubits. Ten model jest szczególnie stosowany w przypadku systemów fizycznych z powiązanymi i lokalnymi interakcjami, ponieważ liczba warunków to $d = \mathcal{O} (\Text{polylog} (N)) $, i może być jasno zapisywana, tj. opisana w sposób klasyczny, w czasie wielomianu.

> [!TIP]
> Hamiltonians, które dzielą się na sumę części, można opisać przy użyciu biblioteki dynamicznej reprezentacji generatora. Aby uzyskać więcej informacji, zobacz sekcję reprezentacja generatora dynamicznego w temacie [struktury danych](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algorytmy symulacji ###

Algorytm symulacji Quantum konwertuje dany opis hamiltonian na sekwencję pierwotnych bram Quantum, które, jako całość, przybliżony czas rozwoju według wspomnianych hamiltonian.

W specjalnym przypadku, gdy hamiltonian dekomponowa w sumie części hermitian, dekompozycja Trotter-Suzuki jest szczególnie prostym i intuicyjnym algorytmem do symulowania Hamiltonians, który rozkłada sumę składników hermitian. Na przykład, Integrator pierwszej kolejności tej rodziny przybliża $ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $ przy użyciu produktu $r d $ terms. 

> [!TIP]
> W przykładach są omówione aplikacje algorytmu symulacji Trotter-Suzuki.
> W przypadku modelu Ising używającego tylko operacji wewnętrznych dostarczonych przez każdą maszynę docelową należy zapoznać się z [przykładem **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> W przypadku modelu Ising przy użyciu struktury kontroli biblioteki Trotter-Suzuki zobacz [przykład **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> W przypadku wodoru molekularnego przy użyciu struktury kontrolki biblioteki Trotter-Suzuki należy zapoznać się z [przykładem **symulacji H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

W wielu przypadkach chcemy zaimplementować algorytm symulacji, ale nie interesuje Cię szczegółowe informacje o jego implementacji. Na przykład, Integrator drugiej kolejności przybliża $ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/2R} e ^ {-IH \_ 1 t/2R} \cdots e ^ {-IH \_ {d-1} t/2R} ^ {-IH \_ {d-1} t/2R} \cdots e ^ {-IH \_ 1 t/2R} e ^ {-IH \_ 0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ | H \_ j \\ | ^ 3 t ^ 3/r ^ 2), \end{align} $ $ przy użyciu produktu $2RD $ terms. Większe zamówienia obejmują jeszcze więcej terminów i zoptymalizowane warianty mogą wymagać bardzo nieuproszczonych porządków wykładniczych. Inne zaawansowane algorytmy mogą również polegać na wykorzystaniu Ancilla qubits w pośrednich krokach. Dlatego algorytmy symulacji pakietów w formacie Canon jako typ zdefiniowany przez użytkownika

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Pierwszy parametr `Double` to czas symulacji, drugi parametr `EvolutionGenerator` , objęty sekcją reprezentacja generatora dynamicznego [struktur danych](xref:microsoft.quantum.libraries.data-structures), to klasyczny opis niezależny od czasu hamiltonian zapakowany z instrukcjami dotyczącymi sposobu symulowania każdego terminu w hamiltonian przez obwód Quantum. Typy tego formularza przybliżą operacje jednostkowe $e ^ {-iHt} $ w trzecim parametrze `Qubit[]` , który jest rejestrem przechowującym stan Quantum symulowanego systemu. Podobnie jak w przypadku przypadków zależnych od czasu, definiujemy typ zdefiniowany przez użytkownika z `EvolutionSchedule` typem, który jest klasyczny opis hamiltonian zależnych od czasu.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Na przykład dekompozycja Trotter-Suzuki może być wywoływana przy użyciu następujących funkcji firmy Canon z parametrami `trotterStepSize` modyfikującymi czas trwania symulacji w każdej wykładniczej i `trotterOrder` dla kolejności wybranego integratora.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Aplikacje biblioteki symulacji zostały omówione w przykładach. Aby oszacować fazę w modelu Ising przy użyciu `SimulationAlgorithm` , zobacz [przykład **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Na potrzeby przygotowania stanu adiabatic w modelu Ising przy użyciu polecenia `TimeDependentSimulationAlgorithm` Zobacz przykład [ **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic przygotowanie stanu & szacowania fazy ###

Jedną z typowych zastosowań symulacji hamiltonian jest adiabatice przygotowanie stanu. W tym miejscu udostępniono dwa Hamiltonians $H \_ {\Text{Start}} $ i $H \_ {\Text{End}} $ oraz stan Quantum $ \ket{\psi (0)} $, który jest stanem uziemienia $H Start hamiltonian \_ {\Text{Start}} $. Zwykle $H \_ {\Text{Start}} $ jest wybierana w taki sposób, że $ \ket{\psi (0)} $ można łatwo przygotować ze stanu podstawy obliczeniowej $ \ket{0\cdots 0} $. Przez interpolację między tymi Hamiltoniansami w przypadku problemów symulacji zależnych od czasu jest to możliwe, aby zakończyć działanie o wysokim prawdopodobieństwie w stanie ziemi końcowego hamiltonian $H \_ {\Text{end}} $. Mimo że przygotowywanie dobrych przybliżeń do Stanów naziemnych hamiltonian może być w ten sposób podejmowane przy użyciu zależnych od czasu algorytmów symulacji hamiltonian jako procedury podrzędnej, inne podejścia koncepcyjnego, takie jak odmiana Quantum eigensolver, są możliwe.

Jeszcze inna aplikacja, która jest powszechnie stosowana w chemii Quantum, szacuje energię stanu ziemi Hamiltonians reprezentującą pośrednie etapy reakcji chemicznej. Taki schemat może na przykład polegać na przygotowaniu stanu adiabatic w celu utworzenia stanu ziemi, a następnie dołączeniu symulacji niezależnej od czasu hamiltonian jako procedury podrzędnej w celu wyodrębnienia tej energii z pewnymi błędami i prawdopodobieństwem sukcesu. 

Abstrakcyjne algorytmy symulacji jako typy zdefiniowane przez użytkownika `SimulationAlgorithm` i `TimeDependentSimulationAlgorithm` pozwalają nam dołączać funkcje do bardziej zaawansowanych algorytmów Quantum. W tym celu należy wykonać te same czynności dla tych często używanych podprocedur.

Dlatego definiujemy wygodną funkcję

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Spowoduje to zwrócenie operacji jednostkowej implementującej wszystkie kroki przygotowania stanu adiabatic. Pierwszy parametr `interpolatedTime` określa czas, przez który liniowo interpoluje się między początkową hamiltonian opisaną przez drugi parametr `evolutionGeneratorStart` i końcowy hamiltonian opisany przez trzeci parametr `evolutionGeneratorEnd` . Czwarty parametr `timeDependentSimulationAlgorithm` polega na tym, że jeden z nich tworzy algorytm symulacji. Należy pamiętać, że jeśli `interpolatedTime` jest wystarczająco długi, początkowy stan uziemienia pozostaje stan chwilowy hamiltonian przez cały czas trwania symulacji zależnej od czasu i w związku z tym kończy się w stanie uziemienia hamiltonian końcowego.

Definiujemy również przydatną operację, która automatycznie wykonuje wszystkie kroki typowego eksperymentu z chemią Quantum. Na przykład mamy następujące elementy, które zwracają oszacowanie energii stanu utworzonego przez przygotowanie adiabatic stanu:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits`jest liczbą qubits używaną do kodowania początkowego stanu Quantum. `statePrepUnitary`przygotowuje stan rozpoczęcia od podstaw obliczeniowej $ \ket{0\cdots 0} $. `adiabaticUnitary`jest operacją jednostkową implementującą przygotowanie stanu adiabatic, na przykład wytwarzany przez `InterpolatedEvolution` funkcję. `qpeUnitary`jest operacją jednostkową, która jest używana do wykonywania oszacowania fazy na wynikającym stanie Quantum. `phaseEstAlgorithm`to nasz wybór algorytmu szacowania fazy.

> [!TIP]
> Aplikacje adiabaticego stanu są omówione w przykładach. W przypadku modelu Ising przy użyciu ręcznej implementacji przygotowania stanu adiabatic przy użyciu `AdiabaticEvolution` funkcji należy zapoznać się z [przykładem **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Aby oszacować fazę i przygotowanie stanu adiabatic w modelu Ising, zobacz [przykład **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> [Symulacja wodoru wodór](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) jest ciekawym i zwięzłym przykładem. Model i wyniki eksperymentalne zgłoszone w [O'Malley et. Al.](https://arxiv.org/abs/1512.06860) wymaga tylko macierzy Pauli i przyjmuje postać $ \hat H = g \_ {0} I \_ 0I \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {Z \_ 1} + g \_ 3 {z \_ 0} {z \_ 1} + g \_ 4 {t \_ 0} {y \_ 1} + g \_ 5 {x \_ 0} {X \_ 1} $. Jest to efektywne hamiltonian tylko 2 qubits, gdzie stałe $g $ są obliczane z odległości $R $ między dwoma atomami wodoru. Korzystając z funkcji firmy Canon, Paul jest konwertowany na unitaries, a następnie rozwijany w krótkim okresie czasu przy użyciu dekompozycji Trotter-Suzuki. Dobre przybliżenie do $H stanu ziemi $ uziemienia można utworzyć bez użycia przygotowania stanu adiabaticu, dlatego energia stanu ziemi może być znaleziona bezpośrednio przez wykorzystanie oszacowania fazy z firmy Canon.

## <a name="shors-algorithm"></a>Algorytm Shora ##
Algorytm skró pozostaje jednym z najbardziej znaczących zmian w zakresie przetwarzania w modelu Quantum, ponieważ wykazał, że komputery z systemem Quantum mogą być używane do rozwiązywania ważnych, obecnie w sposób klasycznych problemów z problemami.
Algorytm skró zapewnia szybki sposób wykorzystania dużych liczb przy użyciu komputera z systemem Quantum, o nazwie *factoring*.
Bezpieczeństwo wielu codziennych Cryptosystems opiera się na założeniu, że nie istnieje szybki algorytm do refaktoryzacji.
Dlatego algorytm skró miał głęboki wpływ na to, jak sądzimy o zabezpieczeniach w świecie w urzędzie Quantum.

Algorytm skró może być uważany za algorytm hybrydowy.
Komputer z systemem Quantum jest używany do wykonywania obliczeniowego zadania trwałego znanego jako wyszukiwanie okresów.
Wyniki wyszukiwania okresu są następnie przetwarzane w sposób klasyczny w celu oszacowania czynników.
Omawiamy poniższe dwa kroki.

### <a name="period-finding"></a>Wyszukiwanie okresów ###

Po zapoznaniu się z działaniem oceny Quantum Fouriera i oszacowaniem fazy (zobacz [algorytmy Quantum](xref:microsoft.quantum.libraries.standard.algorithms)) można użyć tych narzędzi do rozwiązywania problemów z *pewnymi*problemami.  W następnej sekcji zobaczymy, jak zastosować wyszukiwanie okresu do refaktoryzacji.

Podano dwie liczby całkowite $a $ i $N $, gdzie $a<N $, cel szukania okresu, nazywane również kolejnością szukania, to znalezienie _zamówienia_ $r $ z $a $ modulo $N $, gdzie $r $ jest zdefiniowana jako najmniejsza dodatnia liczba całkowita, która $a ^ r \equiv 1 \Text{mod} N $.  

Aby znaleźć kolejność przy użyciu komputera z systemem Quantum, możemy użyć algorytmu szacowania fazy stosowanego do poniższego operatora $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \Text{mod} N}. $ $ eigenvectors $U _a $ są dla liczby całkowitej $s $ i $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pi i sk} {r}} \ket{a ^ k\text {mod} N}, $ $ są _eigenstates_ z $U _A $.
Eigenvalues $U _a $ to $ $ U \_ \ket{x \_ s} = e ^ {2 \ pi i s/r} \ket{x \_ s}. $$

Oszacowanie fazy w ten sposób wyprowadza eigenvalues $e ^ {2 \ pi i s/r} $, z którego $r $ można wydajniej poznać przy użyciu [ciągłego ułamków](https://en.wikipedia.org/wiki/Continued_fraction) z $s/r $.

Diagram obwodu dla wyszukiwania okresu Quantum to:

![Diagram obwodu dla wyszukiwania okresu Quantum](~/media/QPE.svg)

W tym miejscu $2n $ qubits są inicjowane do $ \ket {0} $, a $n $ qubits są inicjowane do $ \ket {1} $.
Czytelnik ponownie może się zastanawiać, dlaczego rejestr Quantum do przechowywania eigenstates jest zainicjowany do $ \ket {1} $.
Ponieważ nikt nie wie, że zamówienie $r $ z wyprzedzeniem, nie można rzeczywiście przygotować bezpośrednio Stanów $ \ket{x_s} $.
Na szczęście, że spowoduje to wymienienie wartości $1/\ sqrt {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket {1} $.
Nie musimy faktycznie przygotowywać $ \ket{x} $!
Można po prostu przygotować rejestr Quantum $n $ qubits w stanie $ \ket {1} $. 

Obwód zawiera QFT i kilka bram, które są kontrolowane.
Brama QFT została [wcześniej](xref:microsoft.quantum.libraries.standard.algorithms)opisana.
Kontrolowane $U _a $ Gate Maps $ \ket{x} $ do $ \ket{(AX) \Text{mod} N} $, jeśli qubit kontrolki to $ \ket {1} $ i Maps $ \ket{x} $ do $ \ket{x} $ w przeciwnym razie.

Aby osiągnąć $ (a ^ NX) \Text{mod} N $, można po prostu zastosować kontrolowane $U _ {a ^ N} $, gdzie obliczamy $a ^ n \Text{mod} N $ w trybie klasycznym, aby podłączyć obwód do obwodu Quantum.  
Obwody do osiągnięcia takich modularnych arytmetycznych zostały opisane w [dokumentacji arytmetycznej](./algorithms.md#arithmetic), w związku z czym potrzebujemy modularnego obwodu wykładniczego, aby zaimplementować operacje kontrolowane $U \_ {a} $.

Chociaż obwód powyżej odnosi się do [szacowania fazy Quantum](xref:microsoft.quantum.characterization.quantumphaseestimation) i jawnie włącza wyszukiwanie zamówień, można zmniejszyć liczbę wymaganych qubits. Możemy użyć metody Beauregard, aby znaleźć kolejność wyszukiwania zgodnie z opisem [na stronie 8 ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), lub skorzystać z jednej z procedur szacowania fazy dostępnych w Microsoft. Quantum. charakteryzującą. Na przykład [niezawodna Ocena fazy](xref:microsoft.quantum.characterization.robustphaseestimation) używa również jednej dodatkowej qubit.
 
### <a name="factoring"></a>Wyprowadzenie ###
Celem jest określenie dwóch czynników zasadniczych liczby całkowitej $N $, gdzie $N $ jest numerem $n $-bitowym.  
Refaktoryzacja składa się z kroków opisanych poniżej. Kroki są podzielone na trzy części: klasyczne procedury przetwarzania wstępnego (1-4); Procedura przetwarzania Quantum, aby znaleźć kolejność $a \Text{mod} N $ (5); i klasyczną dostosujeszą procedurę, aby uzyskać podstawowe czynniki z porządku (6-9).

Procedura klasycznego przetwarzania wstępnego składa się z następujących kroków:
1. Jeśli $N $ jest parzysta, zwróć czynnik podstawowy $2 $.
2. Jeśli $N = p ^ q $ dla $p \geq1 $, $q \geq2 $, zwróć czynnik podstawowy $p $.  Ten krok jest wykonywany w trybie klasycznym.
3. Wybierz liczbę losową $a $ na przykład, że $1 < < N-$1.
4. Jeśli $ \Text{GCD} (a, N) >$1, zwróć czynnik podstawowy $ \Text{GCD} (a, N) $. Ten krok jest obliczany przy użyciu algorytmu Euklidesa.
Jeśli żaden czynnik podstawowy nie został zwrócony, przejdziemy do procedury Quantum:
5. Wywołaj algorytm wyszukiwania okresu Quantum, aby obliczyć kolejność $r $ of $a \Text{mod} N $. Użyj $r $ w klasycznej procedurze dostosujesz, aby określić podstawowe czynniki:
6. Jeśli $r $ jest nieparzysta, Wróć do kroku przetwarzania wstępnego (3).
7. Jeśli $r $ jest parzysta i $a ^ {r/2} =-1 \ Text {mod} N $, Wróć do kroku przetwarzania wstępnego (3).
8. Jeśli $ \Text{GCD} (^ {r/2} + 1, N) $ jest nieprostym czynnikiem $N $, zwróć $ \Text{GCD} (^ {r/2} + 1, N) $.
9. Jeśli $ \Text{GCD} (^ {r/2}-1, N) $ jest nieprostym czynnikiem $N $, zwróć $ \Text{GCD} (^ {r/2}-1, N) $.


Algorytm refaktoryzacji to probabilistyczne: może być pokazywany, że z prawdopodobieństwem co najmniej jedna połowa, która $r $, będzie parzysta i $a ^ {r/2} \neq-1 \Text{mod} N $, dzięki czemu jest to czynnik podstawowy.  (Zobacz [oryginalny dokument skró](https://doi.org/10.1109/SFCS.1994.365700) , aby uzyskać szczegółowe informacje, lub jeden z *podstawowych tekstów przetwarzania Quantum* w programie, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information)).
Jeśli czynnik podstawowy nie jest zwracany, po prostu Powtórzmy algorytm od kroku (1).  Po $n $ próby, prawdopodobieństwo, że każda próba nie powiodła się, jest najwyżej $2 ^ {-n} $.
W takim przypadku po powtarzaniu algorytmu niewielka liczba sukcesów jest praktycznie gwarantowana.
