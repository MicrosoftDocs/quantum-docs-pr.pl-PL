---
title: Qubit w ramach przetwarzania Quantum
description: Dowiedz się więcej na temat qubits, podstawowej jednostki informacji w ramach przetwarzania Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 833c9649b7fbcf8b9fde62c37246b9345fe59a92
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630355"
---
# <a name="the-qubit"></a>Qubit

Podobnie jak bity są podstawowym obiektem informacji w środowisku klasycznym, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum bity) to podstawowy obiekt informacji w ramach przetwarzania Quantum.  Aby zrozumieć tę zgodność, przyjrzyjmy się najprostszym przykładowi: pojedynczemu qubit.

## <a name="representing-a-qubit"></a>Reprezentuje qubit

Podczas gdy bit lub cyfra binarna może mieć wartość $0 $ lub $1 $ , qubit może mieć wartość, która jest albo jedną z tych lub najgłębiej quantum dla $0 $ i $1 $ .

Stan pojedynczej qubit można opisać przy użyciu dwuwymiarowej wektora kolumn w normie, czyli wielkości kwadratu jej wpisów, która musi być sumą do $1 $ . Ten wektor, zwany wektorem stanu Quantum, zawiera wszystkie informacje potrzebne do opisania qubit systemu Quantum, podobnie jak pojedynczy bit zawiera wszystkie informacje potrzebne do opisania stanu zmiennej binarnej.

Każdy dwuwymiarowy wektor kolumn o liczbie rzeczywistej lub złożonej z normą $1 $ reprezentuje możliwy stan Quantum przechowywany przez qubit. W ten sposób $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $ reprezentuje stan qubit, jeśli $ \Alpha $ i $ \beta $ są liczbami złożonymi spełniającymi wartość $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ . Niektóre przykłady prawidłowych wektorów stanu Quantum reprezentujące qubits obejmują

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } , \Text { i} \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } . $ $

Wektory stanu Quantum $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ i $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ mają specjalną rolę. Te dwa wektory stanowią podstawę dla przestrzeni wektorowej opisującą stan qubit. Oznacza to, że każdy wektor stanu Quantum może być zapisany jako suma tych wektorów. W szczególnych przypadkach wektor $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ można napisać jako $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Chociaż każdy obrót tych wektorów będzie działał jako idealnie ważna podstawa dla qubit, wybieramy takie uprawnienia, przez wywołanie go na *podstawie obliczeniowej*.

Przyjmujemy dwa stany Quantum, aby odpowiadały dwóm stanom klasycznego bitu, mianowicie $0 $ i $1 $ . Standardową Konwencją jest wybór

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , $ $

Chociaż przeciwny wybór może być równie dobrze zajęty. Z tego względu nieograniczoną liczbę możliwych wektorów dwuqubitowych w stanie Quantum, tylko dwa odpowiadają stanom klasycznych bitów; wszystkie inne Stany Quantum nie są.

## <a name="measuring-a-qubit"></a>Mierzenie elementu qubit

Teraz, gdy wiemy, jak reprezentować qubit, możemy uzyskać część Intuition dla tego, co reprezentuje te Stany, omawiając koncepcję [*pomiaru*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Pomiar odnosi się do nieformalnego pomysłu "Szukaj" w qubit, który natychmiast zwija stan Quantum do jednego z dwóch stanów klasycznych $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ lub $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Gdy qubit określony przez element Quantum State Vector $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $ jest mierzony, uzyskujemy wynik $0 $ z prawdopodobieństwem $ | \Alpha | ^ 2, $ wynik $1 $ z prawdopodobieństwem $ | \beta | ^ 2 $ . W wyniku $0 $ nowy stan qubit to $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; w wyniku $1 $ jego stan to $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Należy zauważyć, że te prawdopodobieństwa są sumowane do $1 ze $ względu na warunek normalizacji $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Właściwości pomiaru oznaczają również, że ogólny znak wektora stanu Quantum jest nieistotny. Negacja wektora jest równoważna z $ \Alpha \rightarrow-\Alpha $ i $ \beta \rightarrow-\beta $ . Ponieważ prawdopodobieństwo mierzenia wartości $0 $ i $1 $ zależy od wielkości kwadratowej warunków, wstawianie takich znaków nie powoduje zmiany prawdopodobieństwa. Takie fazy są zwykle nazywane [ `` *etapami globalnymi*""](https://en.wikipedia.org/wiki/Phase_factor) i bardziej ogólnie mogą mieć postać $e ^ {i \phi } $, a nie tylko $ \Pm 1 $ .

Ostateczną istotną właściwością miary jest to, że nie musi to spowodować uszkodzenia wszystkich wektorów stanu Quantum. Jeśli zaczynamy od qubit w stanie $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $, który odnosi się do stanu klasycznego $0 $ , zmierzenie tego stanu zawsze zwróci wynik $0 $ i pozostaw stan Quantum niezmieniony. W tym sensie, jeśli mamy tylko klasyczne bity (tj. qubits, które są $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ lub $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $), wówczas pomiar nie uszkodzi systemu. Oznacza to, że możemy replikować klasyczne dane i manipulować nimi na komputerze z systemem Quantum, tak jak można to zrobić na klasycznym komputerze. Jednak możliwość przechowywania informacji w obu Stanach jednocześnie jest podwyższana, co jest możliwe, aby w sposób klasyczny i bardziej ROBS komputery z systemem Quantum mogły kopiować dane Quantum w nieznacznie widoczny sposób, zobacz również [theorem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Wizualizacja Qubits i transformacji przy użyciu sfery Bloch

Qubits może również być postawiony w $3 $ D przy użyciu reprezentacji [*sfery Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  Sfera Blocha pozwala na opisywanie jednowymiarowej, jednokierunkowej, złożonej wektora, jako trójwymiarowej wartości wektorowej.  Jest to ważne, ponieważ pozwala nam na wizualizację jednoqubitowych Stanów, a tym samym opracowywanie przyczyn, które mogą być niecenne w zrozumieniu Stanów wieloqubitowych (gdzie niestety reprezentacje Bloch Sphere nie działa).  Sfera Bloch można wizualizować w następujący sposób:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch sfera](~/media/concepts_bloch.png)

Strzałki na tym diagramie pokazują kierunek, w którym wektor stanu Quantum jest wskazywany, a każda transformacja strzałki może być uważana za rotację na jednej z osi kardynalnych.
Chociaż zastanawiasz się, że obliczenia Quantum są rozbudowane Intuition, trudne jest użycie tego Intuition do projektowania i opisywania algorytmów. Q # eliminuje ten problem, dostarczając język do opisywania takich rotacji.

## <a name="single-qubit-operations"></a>Operacje pojedynczej qubit

Komputery Quantum przetwarzają dane przez zastosowanie uniwersalnego zestawu bram Quantum, które mogą emulować każdy obrót wektora stanu Quantum.
To pojęcie uniwersalności jest zbliżone na potrzeby uniwersalności dla tradycyjnych (tj. klasycznych) obliczeń, w których zestaw bram jest uznawany za uniwersalny, jeśli każda transformacja bitów wejściowych może zostać wykonana przy użyciu obwodu o skończonej długości.
W przypadku przetwarzania Quantum prawidłowe przekształcenia, które możemy wykonywać na qubit są transformacje jednostkowe i pomiary.
*Podległych operacja* lub złożona sprzężona transformacja ma decydujące znaczenie dla przetwarzania Quantum, ponieważ jest to konieczne do odwrócenia transformacji Quantum.
Polecenie Q # odzwierciedla to poprzez dostarczenie metod automatycznego kompilowania sekwencji bram do ich sąsiadujących, co sprawia, że programista chce, aby adjoints kod w wielu przypadkach. Poniżej przedstawiono przykład:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Chociaż jest to prosty przykład (jak <xref:microsoft.quantum.intrinsic.h>  operacja jest samodzielna), można zobaczyć, w jaki sposób to nie będzie cenne dla bardziej skomplikowanych operacji qubit.
Aby uzyskać więcej informacji, zobacz [operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions).

Istnieje tylko cztery funkcje, które mapują jeden bit na jeden bit na klasycznym komputerze. W przeciwieństwie do jednego qubit na komputerze Quantum istnieje nieskończona liczba transformacji jednostkowych. W związku z tym nie ma skończonego zestawu podstawowych operacji Quantum, nazywane [*bramami*](https://en.wikipedia.org/wiki/Quantum_logic_gate), może dokładnie replikować nieskończony zestaw przekształceń jednostkowych dozwolony w przypadku przetwarzania Quantum. Oznacza to, że w przeciwieństwie do klasycznych obliczeń nie jest możliwe, aby komputer Quantum mógł zaimplementować każdy możliwy program Quantum dokładnie przy użyciu skończonej liczby bram. Tym samym komputery Quantum nie mogą być uniwersalne w tym samym sensie klasycznych komputerów. W związku z tym, że zestaw bram jest *uniwersalny* na potrzeby przetwarzania w ramach usługi Quantum, firma Microsoft znaczy nieco słabo słabsze niż w przypadku klasycznego przetwarzania danych.
W celu zapewnienia uniwersalnego wymaga się, aby komputer Quantum był *przybliżony* tylko dla każdej macierzy jednostkowej w ramach skończonego błędu przy użyciu sekwencji bramy o skończonej długości.
Innymi słowy, zestaw bram jest uniwersalnym zestawem bram, jeśli jakakolwiek transformacja jednostkowa może być w przybliżeniu zapisywana jako iloczyn bram z tego zestawu. Potrzebujemy, aby dla dowolnego z określonych błędów określono bramy $G _ {1 } , G_ {2 } , \ldots, G_N $ z zestawu bram, tak że

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

Należy zauważyć, że ze względu na to, że Konwencja do mnożenia macierzy ma być mnożona od prawej do lewej strony pierwszej bramy w tej sekwencji, $G _N $ , jest faktycznie ostatnim zastosowaniem do wektora stanu Quantum. Bardziej formalnie Załóżmy, że taki zestaw bram jest uniwersalny, jeśli dla każdej tolerancji błędu $ \epsilon>0 $ istnieje $G _1, \ldots G_N $ taki, że odległość między $G _N \ldots G_1 $ i $U $ jest najwyżej $ \epsilon $ . Najlepiej, aby wartość $N $ wymagana do osiągnięcia tej odległości elementu $ \epsilon $ powinna mieć skalę Poly-logarithmically z $1/\ Epsilon $ .

Co to jest uniwersalny zestaw bram, który wygląda jak w przypadku?  Najprostsza taka Uniwersalna brama dla bram qubit składa się tylko z dwóch bram: bramy Hadamard $H $ i tak zwanej bramy $T $ -Gate (znanej także jako brama $ \ pi/8 $ ):

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ Pi/4 } \end{ bmatrix } .
$$

Jednak ze względu na praktyczne powody dotyczące korekcji błędów Quantum może być wygodniejszy do uwzględnienia większego zestawu bram, a mianowicie tego, który można wygenerować przy użyciu $H $ i $T $ .
Można sklasyfikować bramy Quantum na dwie kategorie: bramy Clifford i $ bramę $T.
Ten podział jest przydatny, ponieważ w wielu schematach korekcji błędów Quantum tak zwane bramy Clifford są łatwe do zaimplementowania, które wymagają bardzo kilku zasobów w zakresie operacji i qubits, aby zapewnić odporność na uszkodzenia, a bramy nieCliffordowe są dość kosztowne przy wymaganiu odporności na uszkodzenia. Standardowy zestaw bram Clifford z pojedynczą qubitą [uwzględnionych domyślnie w Q #](xref:microsoft.quantum.libraries.standard.prelude)obejmuje

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2, \qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4H, $ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ i & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4.
$$

W tym miejscu $X operacje $ , $Y $ i $Z $ są używane szczególnie często i są nazwanymi [*operatorami Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) po ich twórcy Wolfgang Pauli.
Wraz z bramą nieCliffordową ( $ bramą $T) te operacje mogą być składane, aby przybliżyć każdą transformację jednostkową na pojedynczym qubite.

Aby uzyskać więcej informacji na temat tych operacji, ich reprezentacje sfery Bloch i implementacje Q #, zobacz [operacje wewnętrzne i funkcje](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Przykładem sposobu, w jaki można kompilować przekształcenia jednostkowe z tych elementów pierwotnych, trzy przekształcenia przedstawione powyżej w sferze Bloch odpowiadają sekwencji bramy $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $.

Mimo że poprzednie tworzą najpopularniejsze bramy pierwotne do opisywania operacji na poziomie logicznym stosu (należy traktować poziom logiczny jako poziom algorytmu Quantum), często warto rozważyć mniejsze podstawowe operacje na poziomie algorytmu, na przykład operacje bliżej poziomu opisu funkcji. Na szczęście polecenie Q # ma także dostępne metody implementowania unitaries wyższego poziomu, co z kolei zezwala na implementowanie algorytmów wysokiego poziomu bez jawnego tworzenia wszystkiego w dół do Clifford i $T $ -bram.

Najprostsza taka pierwotna to qubit. Trzy rotacje pojedynczej qubit są zwykle uznawane za: $R _x $ $R _Y $ i $R _Z $ . Aby wizualizować akcję rotacji $R _x (\theta) $, na przykład Wyobraź sobie, że znajduje się prawy kciuk wzdłuż kierunku $ osi $x sfery Bloch i obracania wektora z ręką przy użyciu kąta $ \ teta/2 $ radianów. Ten mylący współczynnik $2 $ wynika z faktu, że wartości wektorów ortogonalnych są równe $180 ^ \circ $ , gdy są kreślone w sferze Bloch, ale rzeczywiście są w rzeczywistości $90 ^ \circ $ stopniach geometrycznych. Odpowiednie macierze jednostkowe są następujące:

\begin{align *} &R_z (\theta) = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ teta/2 } & 0 \\\\ 0 & e ^ {i \ teta/2 } \end{ bmatrix } , \\ \\ &R_x (\theta) = e ^ {-i\theta x/2 } = HR_z (\theta) H = \begin{ bmatrix } \cos (\ teta/2) &-i\sin (\ teta/2) \\ \\ -i\sin (\ teta/2) & \cos (\ teta/2) \end{ bmatrix } , \\ \\ &R_y (\theta) = e ^ {-i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{ bmatrix } \cos (\ teta/2) &-\sin (\ teta/2) \\ \\ \sin (\ teta/2) & \cos (\ teta/2) \end{ bmatrix } . \end{align*}

Podobnie jak każde trzy obroty mogą być połączone ze sobą w celu przeprowadzenia dowolnego obrotu w trzech wymiarach, może być widoczne z reprezentacji sfery Bloch, że każda macierz jednostkowa może być zapisywana jako sekwencja trzech rotacji. W odniesieniu do każdej macierzy jednostkowej $U $ istnieje $ \Alpha, \beta, \gamma, \delta, $ która $U = e ^ {i \alpha } R_x (\beta) R_z (\gamma) R_x (\delta) $. W związku z tym $R _z (\theta) $ i $H $ również tworzą uniwersalny zestaw bram, chociaż nie jest to zestaw dyskretny, ponieważ element $ \theta $ może przyjmować dowolną wartość. Z tego powodu i ze względu na aplikacje w symulacji Quantum, takie ciągłe bramy są kluczowe dla obliczeń Quantum, szczególnie na poziomie projektowania algorytmu Quantum. Aby osiągnąć implementację sprzętu odpornego na błędy, ostatecznie zostaną one skompilowane do odrębnych sekwencji bram, które ściśle przybliżą te rotacje.
