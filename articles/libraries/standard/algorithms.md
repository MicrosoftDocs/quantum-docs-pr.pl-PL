---
title: 'Algorytmy Quantum w Q #'
description: Poznaj podstawowe algorytmy przetwarzania Quantum, w tym wzmocnienie amplitudy, transformację Fouriera, Draper i Beauregard, a także oszacowania faz.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 8b8a9019e8bc419f42b0c6f7558354d19a157917
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402854"
---
# <a name="quantum-algorithms"></a>Algorytmy Quantum #

## <a name="amplitude-amplification"></a>Wzmacnianie amplitudy ##

*Wzmocnienie amplitudy* to jedno z podstawowych narzędzi przetwarzania Quantum. Jest to podstawowe koncepcje, które opierają się na wyszukiwaniu Grover, ocenie amplitudy i wielu algorytmach uczenia maszynowego Quantum.  Istnieje wiele wariantów i w sekcji Q # udostępniamy ogólną wersję opartą na wzOblivious amplitudy ze środkami częściowymi, aby zapewnić szeroką część zastosowań.

Centralnym pomysłem związanym z wzmocnieniem amplitudy jest wzmocnienie prawdopodobieństwa pożądanego wyniku, wykonując sekwencję odbicia.  Te odbicia obracają stan początkowy bliżej żądanego stanu docelowego, często nazywanego stanem oznaczonym.  W przypadku, gdy prawdopodobieństwo mierzenia stanu początkowego w oznaczonym stanie to $ \sin ^ 2 (\theta) $, po zastosowaniu wzmocnienia amplitudy $m $ razy prawdopodobieństwo sukcesu stanie się $ \sin ^ 2 ((2 mln + 1) \theta) $.  Oznacza to, że jeśli $ \theta = \ pi/[2 (2n + 1)] $ dla pewnych wartości $n $, wzmocnienie amplitudy może zwiększyć prawdopodobieństwo sukcesu do $100\\% $ po $n $ iteracji wzmocnienia amplitudy.  Ponieważ $ \theta = \sin ^{-1}(\sqrt{\Pr (Success)}) $ oznacza to, że liczba iteracji, które są konieczne do uzyskania sukcesu, jest mniejsza niż oczekiwana liczba wymagana do znalezienia oznaczonego stanu, która jest niedeterministyczna przy użyciu losowego próbkowania.

Każda iteracja wzmocnienia amplitudy wymaga określenia dwóch operatorów odbicia. W przypadku $Q $ jest iteracja wzmocnienia amplitudy i $P _0 $ jest operatorem rzutnika w miejscu początkowym i $P _1 $ jest projektorem w oznaczonym miejscu, a następnie $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Wycofaj, że projektor jest operatorem hermitian, który ma eigenvalues $ + $1 i $0 $ i jako wynik $ (\boldone-2P_0) $ jest jednostką, ponieważ ma eigenvalues, które są korzeniami aparatu Unity (w tym przypadku $ \Pm $1). Przykładowo Rozważmy przypadek wyszukiwania Grover z początkowym stanem $H ^ {\otimes n} \ket{0}$ i oznaczonym stanem $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ i $P _1 = \ket{m}\bra{m} $.  W większości zastosowań wzmocnienia amplitudy $P _0 $ będzie projektorem w stanie początkowym, co $P _0 = \boldone-2 \ KET {\ psi} \ bra {\ psi} $ dla niektórych wektorów $ \ket{\psi} $; Jednak w przypadku Oblivious amplitudy amplication $P _0 $ będzie zazwyczaj projektować w wielu stanach Quantum (tj. liczebność $ + $1 eigenvalue $P _0 $ jest większy niż $1 $).

Logika za wzmocnieniem amplitudy następuje bezpośrednio z eigenego dekompozycji $Q $.  W odniesieniu do eigenvectors $Q $, że stan początkowy ma niezerową pomoc techniczną, można pokazać, że są to liniowe kombinacje $ + $1 eigenvectors $P _0 $ i $P _1 $.  W odniesieniu do stanu początkowego wzmocnienia amplitudy (przy założeniu, że jest to $ + $1 eigenvector $P _0 $) można napisać jako $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left (e ^ {i\theta} \ KET {\ psi_ +} + e ^ {-i\theta} \ KET {\ psi_-} \right), $ $ WHERE $ \ket{\ psi_ \Pm} $ to eigenvectors of $Q $ with eigenvalues $e ^ {\Pm 2i \ teta} $ i ma pomoc techniczną dla $ + $1 eigenvectors of $P _0 $ i $P _1 $.  Fakt, że eigenvalues są $e ^ {\Pm i \theta} $ oznacza, że operator $Q $ wykonuje obrót w dwuwymiarowym miejscu, określonym przez dwa projektory i początkowym stanie, w którym kąt obrotu to $2 \ TETA $.  To dlatego po $m $ iteracji $Q $ prawdopodobieństwo sukcesu to $ \sin ^ 2 ([2 mln + 1] \theta) $.

Inną przydatną właściwością, która pochodzi z tego, jest to, że eigenvalue $ \theta $ jest bezpośrednio związany z prawdopodobieństwem, że stan początkowy zostanie oznaczony (w przypadku, gdy $P _0 $ jest projektorem tylko w stanie początkowym).  Ponieważ eigenphases $Q $ to $2 \ teta = 2 \ Sin ^{-1}(\sqrt{\Pr (Success)}) $, wtedy, gdy stosujemy szacowanie fazy do $Q $, możemy poznać prawdopodobieństwo sukcesu dla procedury jednostki Quantum.  Jest to przydatne, ponieważ wymaga dwukwadratowych zastosowań procedury Quantum, aby poznać prawdopodobieństwo sukcesu, niż byłoby to konieczne.

Q # wprowadza wzmocnienie amplitudy jako specjalizację wzmocnienia amplitudy Oblivious.  Wzmocnienie amplitudy Oblivious zdobywa ten moniker, ponieważ projektor na początku eigenspace nie musi być projektorem w stanie początkowym.  W tym sensie protokół jest Oblivious do stanu początkowego.  Najważniejszym zastosowaniem wzmocnienia amplitudy Oblivious jest w niektórych *liniowych kombinacjach* metod symulacji hamiltonian jednostkowych, w którym stan początkowy jest nieznany, ale zmienia się Entangled za pomocą rejestru Ancilla w protokole symulacji.  Jeśli ten rejestr Ancilla był mierzony jako wartość stała, powiedzmy $0 $, a następnie takie metody symulacji stosują odpowiednią transformację jednostkową do pozostałej części qubits (nazywanej rejestrem systemu).  Wszystkie inne wyniki pomiarów mogą jednak prowadzić do błędu.  Wzmocnienie amplitudy Oblivious umożliwia zwiększenie prawdopodobieństwa sukcesu tego pomiaru do $100\\% $ z powyższymi przyczynami.  Ponadto zwykłe wzmocnienie amplitudy odnosi się do przypadku, w którym rejestr systemu jest pusty.  To dlatego, że funkcja Q # używa wzmocnienia amplitudy Oblivious jako swojej podstawowej procedury wzmocnienia amplitudy.

Procedura ogólna (`AmpAmpObliviousByReflectionPhases`) zawiera dwa rejestry, które są wywoływane `ancillaRegister` i `systemRegister`. Akceptuje również dwie Oracle w celu zaakceptowania niezbędnych odbić. `ReflectionOracle` działa tylko na `ancillaRegister`, podczas gdy `ObliviousOracle` działa wspólnie dla obu rejestrów. Dane wejściowe do `ancillaRegister` muszą być zainicjowane do-1 eigenstate pierwszego operatora odbicia $ \boldone-2P_1 $.

Zazwyczaj firma Oracle przygotowuje stan w oparciu o podstawę obliczeniową $ \ket{0...0} $. W naszej implementacji `ancillaRegister` składają się z jednej qubit (`flagQubit`), która kontroluje `stateOracle` i resztę żądanego ancillasu. `stateOracle` jest stosowany, gdy `flagQubit` jest $ \ket{1}$.

Może również dostarczyć Oracle `StateOracle` i `ObliviousOracle` zamiast odbijających przez wywołanie `AmpAmpObliviousByOraclePhases`.

Jak wspomniano, tradycyjne wzmocnienie amplitudy jest tylko szczególnym przypadkiem tych procedur, w których `ObliviousOracle` jest operatorem tożsamości i nie ma żadnych qubits systemowych (tj. `systemRegister` jest puste). Jeśli chcesz uzyskać fazy dla częściowego odbicia (np. dla wyszukiwania Grover), funkcja `AmpAmpPhasesStandard` jest dostępna. Zapoznaj się z `DatabaseSearch.qs`, aby zapoznać się z przykładową implementacją algorytmu Grover.

W przypadku etapów obrotu pojedynczej qubit są powiązane fazy operatora odbicia, zgodnie z opisem w dokumencie przez [G.H. Low, I. L. Czuang](https://arxiv.org/abs/1707.05391). Stosowane fazy stałego punktu są szczegółowo opisane w [Yoder, niskiej i Czuang](https://arxiv.org/abs/1409.3305) wraz z fazami w [niskiej, Yoder i Czuang](https://arxiv.org/abs/1603.03996).

W przypadku tła można zacząć od [wzmocnienia amplitudy standardowej](https://arxiv.org/abs/quant-ph/0005055) , a następnie przejść do wprowadzenia do [wzmocnienia amplitudy Oblivious](https://arxiv.org/abs/1312.1414) i wreszcie generalizacje prezentowane w [niskiej i Czuang](https://arxiv.org/abs/1610.06546). Przykładowa Prezentacja tego całego obszaru (w miarę odnosząca się do symulacji hamiltonian) została pobrana przez [Dominic jagody](http://www.dominicberry.org/presentations/Durban.pdf).

## <a name="quantum-fourier-transform"></a>Transformacja Fouriera Quantum ##

Transformacja Fouriera to podstawowe narzędzie do klasycznej analizy i jest równie ważne w przypadku obliczeń Quantum.
Ponadto wydajność *transformacji Fouriera* (QFT) w oparciu o liczbę, która jest możliwa na maszynie klasycznej, sprawia, że jest to jeden z pierwszych wybranych narzędzi do projektowania algorytmu Quantum.

Dzięki przybliżonej generalizacji QFT udostępniamy operację <xref:microsoft.quantum.canon.approximateqft>, która pozwala na dalsze optymalizacje przez oczyszczenie rotacji, które nie są absolutnie niezbędne do uzyskania odpowiedniej dokładności algorytmu.
Przybliżona QFT wymaga <xref:microsoft.quantum.intrinsic.rfrac> $Z $-Rotation operacji, a także operacji <xref:microsoft.quantum.intrinsic.h>.
Założono, że dane wejściowe i wyjściowe są zakodowane w big endian kodowania---to oznacza, że qubit z indeksem `0` jest zakodowana w lewym największej liczbie (najwyższa) bitowej binarnej liczbie całkowitej.
Jest to zgodne z [notacją KET](xref:microsoft.quantum.concepts.dirac), ponieważ rejestr trzech qubits w stanie $ \ket{100}$ odpowiada $q _0 $ jest w stanie $ \ket{1}$, $q _1 $ i $q _2 $ są w stanie $ \ket{0}$.
Parametr przybliżenia $a $ określa poziom oczyszczenia $Z $-rotations, czyli $a \In [0.. n] $.
W tym przypadku wszystkie $Z $-rotations $2 \ pi/2 ^ k $, gdzie $k > a $ są usuwane z obwodu usługi QFT.
Wiadomo, że dla $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. jeden może być powiązany z $\\| \operatorname{QFT}-\operatorname{AQFT} \\| < \epsilon $.
W tym miejscu $\\| \cdot\\| $ jest normą operatora, która w tym przypadku jest pierwiastek kwadratowy największego [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) z $ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Arytmetyczny ##

Podobnie jak arytmetyczne odgrywają centralną rolę w środowisku klasycznym, jest również niezbędny w przypadku przetwarzania Quantum.  Algorytmy, takie jak algorytm refaktoryzacji skró, metody symulacji Quantum i wiele algorytmów oracular polegają na spójnych operacjach arytmetycznych.  Większość podejścia do operacji arytmetycznych na podstawie obwodów z dołączaniem Quantum.  Najprostszym obiektem dodającym jest klasyczne dane wejściowe $b $ i dodaje wartość do stanu Quantum przechowującego liczbę całkowitą $ \ket{a} $.  Matematycznie, Metoda dodająca (która oznacza $ \operatorname{Add} (b) $ dla klasycznego wejścia $b $) ma właściwość, która

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Ten podstawowy obwód do dołączania jest większy niż dodający się do dołączenia.
Można go przekonwertować na obiekt dodający, który ma dwa dane wejściowe Quantum przy użyciu $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ przy użyciu $n $ kontrolowane aplikacje do dodających formularzy \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda\_{a\_0} \left (\operatorname{Add} (1) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cdots \Lambda\_{a\_{n-1}} \left (\ operatorname {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} dla $n $-bit Integer $a $ i $b $ i Dodawanie modulo $2 ^ n $.  Odwołaj tę notację $ \Lambda\_x (A) $ odwołuje się do każdej operacji $A $, do kontrolowanej wersji tej operacji z qubit $x $ as Control.

Podobnie kontrolowana w sposób klasyczny sposób mnożenia (modułowy formularz, który jest niezbędny dla algorytmu refaktoryzacji skró) można wykonać przy użyciu podobnej serii kontrolowanych dodatków: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda\_{x\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + AX}.
\end{align} istnieje subtlety z mnożeniem na komputerach z systemem Quantum, które można zauważyć z definicji $ \operatorname{Mult} $ powyżej.  W przeciwieństwie do dodania, wersja Quantum tego obwodu przechowuje produkt danych wejściowych w rejestrze pomocniczym, a nie w rejestrze wejściowym.  W tym przykładzie rejestr jest inicjowany z wartością $b $, ale zazwyczaj zacznie utrzymywać wartość zero.  Jest to niezbędny w przypadku, gdy w ogóle nie istnieje mnożenia dla ogólnych $a $ i $x $.  Ponieważ wszystkie operacje Quantum, Save pomiary, są odwracalnie, musimy zachować wystarczającą ilość informacji, aby odwrócić mnożenie.  Z tego powodu wynik jest przechowywany w oddzielnej tablicy.  Ta część zapisywania danych wyjściowych operacji nieodwracalnych, takich jak mnożenie, w osobnym rejestrze nosi nazwę "Bennett lew" po Charlie Bennett i jest podstawowym narzędziem do przetwarzania w trybie odwracalnym i Quantum.

Zaproponowano wiele obwodów Quantum do dodania, a każda z nich analizuje różne kompromisy pod względem liczby qubits (miejsca) i liczby wymaganych operacji na bramie (czas).  Przeglądamy dwa bardziej wydajne elementy dodające o dużej ilości miejsca, znane jako Draper dodające i Beauregard.

### <a name="draper-adder"></a>Draper ###

Draper dodający jest raczej jednym z najbardziej eleganckich elementów Quantum, ponieważ bezpośrednio wywołuje właściwości Quantum do wykonania.  Wgląd za Draper dodający to, że transformacja Fouriera może służyć do translacji przesunięcia fazy na bit Shift.  Następnie następuje zastosowanie transformacji Fouriera, zastosowanie odpowiedniej fazy zmiany, a następnie cofnięcie przekształcenia Fouriera można zaimplementować.  W przeciwieństwie do wielu innych proponowanych dodających, funkcja Draper Explicit jawnie używa efektów Quantum wprowadzonych przez transformację Quantum Fouriera.  Nie ma naturalnego klasycznego odpowiednika.  Poniżej przedstawiono określone kroki Draper.

Załóżmy, że masz dwa $n $-bitowe qubit rejestrujące przechowywanie liczb całkowitych $a $ i $b $, dla wszystkich $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Jeśli definiujemy $ $ \ket{\phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right), $ $ następnie po niektórych algebry można zobaczyć, że $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 (a)} \otimes \cdots \otimes \ket{\phi\_n (a)}.
$ $ Ścieżka do wykonania obiektu dodającego zostaje wyczyszczona po zaobserwowaniu, że suma danych wejściowych może być zapisywana jako $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 (a + b)} \otimes \cdots \otimes \ket{\phi\_n (a + b)}.
$ $ Liczby całkowite $b $ i $a $ można następnie dodać przez przeprowadzenie rotacji kontrolowanej fazy na każdym z qubits w dekompozycji przy użyciu bitów $b $ as Controls.

To rozwinięcie może być dodatkowo uproszczone przez zanotowanie, że dla dowolnej liczby całkowitej $j $ i liczby rzeczywistej $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Wynika to z faktu, że w przypadku rotacji $360 ^ {\circ} $ stopni ($ 2 \ pi $ RADIANS) w okręgu zostanie precyzyjnie dokończyć pracę.  Jedyną istotną częścią $x $ dla $e ^ {i2\pi x} $ jest w związku z tym ułamkowa część $x $.  W przypadku, gdy mamy rozwinięcie binarne formularza $x = t +0. x\_0x\_2 \ ldots x\_n $, $e ^ {i2\pi x} = e ^ {i2\pi (0. x\_0x\_2 \ ldots x\_{n-1})} $, w związku z czym $ $ \ket{\phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right). $ $ oznacza to, że jeśli wykonujemy Dodawanie przez zwiększenie każdego ze współczynników dwuetapowych w rozwinięciu przekształcenia Fouriera $ \ket{a} $ then Liczba obrotów jest zmniejszana w miarę $k $ maleje.  Znacznie zmniejsza liczbę bram Quantum wymaganych w dodającej.  Notujemy transformację Fouriera, Dodawanie faz i odwrotne kroki transformacji Fouriera, które składają się na Draper dodające jako $ \operatorname{QFT} ^{-1} \left (\phi\\\!\operatorname{ADD}\right) \operatorname{QFT} $. Poniżej można zobaczyć obwód Quantum, który używa tego uproszczenia do implementacji całego procesu.

![Drapere, które są wyświetlane jako diagram obwodu](~/media/draper.svg)

Każda kontrolowana Brama $e ^ {I2 \ pi/k} $ w obwodzie odwołuje się do bramy sterowanej fazy.  Takie bramy mają właściwość, która znajduje się na parze qubits, w której działają, $ \ket{00}\mapsto \ket{00}$, ale $ \ket{11}\mapsto e ^ {I2 \ pi/k} \ KET{11}$.  Obwód ten pozwala nam wykonać Dodawanie przy użyciu żadnych dodatkowych qubits poza tymi, które są konieczne do przechowywania danych wejściowych i wyjściowych.

### <a name="beauregard-adder"></a>Beauregard ###

Beauregard dodający jest modularnym modułem dodający, który korzysta z dodającego Draper, aby wykonać Dodawanie modulo $N $ dla dowolnej wartości dodatniej liczby całkowitej $N $.  Znaczenie modularnych elementów dodających, takich jak Beauregard, jest w dużym stopniu od ich użycia w ramach modularnego etapu potęgowania w algorytmie skró.  Modularna funkcja dodająca Quantum ma następujące działania dla danych wejściowych Quantum $ \ket{b} $ i klasyczne dane wejściowe $a $, gdzie $a $ i $b $ są przypadane jako liczby całkowite mod $N $, co oznacza, że znajdują się w interwale $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{cases}.
$$

Funkcja Beauregard do dopełnienia używa dodającego Draper lub dokładniej $ \phi\\\!\operatorname{ADD} $, aby dodać $a $ i $b $ w fazie.  Następnie używa tej samej operacji, aby określić, czy $a + b < N $ przez odjęcie $N $ i testowanie, jeśli $a + b-N < 0 $.  Obwód przechowuje te informacje w pomocniczej qubit, a następnie dodaje $N $ back a, jeśli $a + b < N $.  Następnie zwalnia ten bit pomocniczy (ten krok jest niezbędny, aby zapewnić, że po wywołaniu funkcji dodającej Ancilla można cofnąć alokację).  Poniżej przedstawiono obwód dla Beauregard.

![Beauregarde, które są wyświetlane jako diagram obwodu](~/media/beau.svg)

W tym miejscu Brama $ \Phi\\\!\operatorname{ADD} $ przyjmuje taką samą formę jak $ \Phi\\\!\operatorname{ADD} $, z wyjątkiem tego w tym kontekście dane wejściowe są klasyczne zamiast Quantum.  Dzięki temu kontrolowane fazy w $ \Phi\\\!\operatorname{ADD} $ do zamienienia na bramy faz, które następnie można kompilować w mniejszej liczbie operacji, aby zmniejszyć liczbę qubits i liczbę bram potrzebnych do dodającego.

Aby uzyskać więcej informacji, zapoznaj się z tematem [M. Roetteler, th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) i [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Szacowanie fazy kwantowej ###

Jednym z szczególnie ważnych zastosowań transformacji Fouriera Quantum jest poznanie eigenvalues operatorów jednostkowych, problemu znanego jako *oszacowanie fazy*.
Rozważ użycie jednostek $U $ i State $ \ket{\phi} $, tak że $ \ket{\phi} $ to eigenstate z $U $ z nieznanym eigenvalue $ \phi $, \begin{Equation} U\ket {\ Fi} = \phi\ket{\phi}.
\end{Equation} Jeśli mamy dostęp do $U $ jako Oracle, możemy poznać fazę $ \phi $, wykorzystując, że $Z $ rotacje zastosowane do obiektu docelowego kontrolowanej operacji propagują do formantu.

Załóżmy, że $V $ jest kontrolowanym zastosowaniem $U $, takich jak \begin{align} V (\ket{0} \otimes \ket{\phi}) & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{i} V (\ket{1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket{1} \otimes \ket{\phi}.
\end{align} następnie, według liniowości, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket{0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket{1} \otimes \ket{\phi})} {\sqrt{2}}.
\end{align} możemy zbierać warunki, aby znaleźć \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align}, gdzie $R _1 $ jest jednostką stosowaną przez operację <xref:microsoft.quantum.intrinsic.r1>.
Inaczej mówiąc, efekt zastosowania $V $ jest dokładnie taki sam jak zastosowanie $R _1 $ z nieznanym kątem, nawet jeśli mamy dostęp tylko do $V $ jako Oracle.
W związku z tym w pozostałej części tej dyskusji będziemy omawiać oszacowania fazy pod względem $R _1 (\phi) $, który implementuje się przy użyciu tak zwanej *fazy KickBack*.

Ponieważ kontrolka i rejestr docelowy pozostają untangled po tym procesie, możemy ponownie użyć $ \ket{\phi} $ jako elementu docelowego kontrolowanej aplikacji $U ^ $2, aby przygotować drugi formant qubit w stanie $R _1 (2 \phi) \ket{+} $.
W ten sposób możemy uzyskać rejestr w formie \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket{0} + \exp (i 2 ^ {j} \phi) \ket{1}\right) \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align}, gdzie $n $ to liczba wymaganych elementów dokładności, a tam, gdzie użyto ${} \propto {}$, aby wskazać, że został pominięty współczynnik normalizacji $1/\sqrt {2 ^ n} $.

Jeśli przyjęto założenie, że $ \phi = 2 \pi p/2 ^ k $ dla liczby całkowitej $p $, rozpoznawamy to jako $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, gdzie $p _j $ to $j ^ {\textrm{th}} $ bit $2 \pi \phi $.
W związku z zastosowaniem sąsiedniej transformacji Fouriera Quantum, firma Microsoft uzyskuje reprezentację binarną fazy zakodowanej jako stan Quantum.

W języku Q # jest to implementowane przez operację <xref:microsoft.quantum.characterization.quantumphaseestimation>, która przyjmuje <xref:microsoft.quantum.oracles.discreteoracle> implementujące stosowanie $U ^ m $ jako funkcji dodatnich liczb całkowitych $m $.
