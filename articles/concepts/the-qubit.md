---
title: qubit w usłudze Quantum Computing Description: Poznaj qubits, podstawową jednostkę informacji w ramach przetwarzania Quantum.
Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. qubit MS. Author: v-benbra MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="the-qubit"></a>Qubit

Podobnie jak bity są podstawowym obiektem informacji w środowisku klasycznym, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum bity) to podstawowy obiekt informacji w ramach przetwarzania Quantum.  Aby zrozumieć tę zgodność, przyjrzyjmy się najprostszym przykładowi: pojedynczemu qubit.

## <a name="representing-a-qubit"></a>Reprezentuje qubit

Podczas gdy bit lub cyfra binarna może mieć wartość $ 0 $ lub $ 1 $ , qubit może mieć wartość, która jest albo jedną z nich, albo z najwyższym ustawieniem Quantum równą $ 0 $ i $ 1 $ .

Stan pojedynczej qubit można opisać przy użyciu dwuwymiarowej wektora kolumn w normie, czyli wielkości kwadratu jej wpisów, która musi być sumą do $ 1 $ . Ten wektor, zwany wektorem stanu Quantum, zawiera wszystkie informacje potrzebne do opisania qubit systemu Quantum, podobnie jak pojedynczy bit zawiera wszystkie informacje potrzebne do opisania stanu zmiennej binarnej.

Każdy dwuwymiarowy wektor kolumn o liczbie rzeczywistej lub zespolonej z normą $ 1 $ reprezentuje możliwy stan Quantum przechowywany przez qubit. W ten sposób $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ reprezentuje stan qubit $ \alpha $ , jeśli i $ \beta $ są liczbami złożonymi spełniającymi wartość $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .   Niektóre przykłady prawidłowych wektorów stanu Quantum reprezentujące qubits obejmują

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ , \end{bmatrix} 1 2, 2 \begin{bmatrix} \frac { } { \sqrt { } } \\\\ \frac { } { \sqrt { } } \end{bmatrix} , 1 \begin{bmatrix} \frac { } { \sqrt { 2 } } \\\\ \frac { -1 } { \sqrt { 2 } } \end{bmatrix} \text { i } \begin{bmatrix} \frac { 1 2 i } { \sqrt { } } \\\\ \frac { } { \sqrt { 2 } } \end{bmatrix} .      $$

Wektory stanu Quantum $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ i $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ mają specjalną rolę. Te dwa wektory stanowią podstawę dla przestrzeni wektorowej opisującą stan qubit. Oznacza to, że każdy wektor stanu Quantum może być zapisany jako suma tych wektorów. W $ \begin{bmatrix} odniesieniu do wektora x \\\\ y \end{bmatrix} $ można napisać jako $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Chociaż każdy obrót tych wektorów będzie działał jako idealnie ważna podstawa dla qubit, wybieramy takie uprawnienia, przez wywołanie go na *podstawie obliczeniowej*.

Przyjmujemy dwa stany Quantum, aby odpowiadać dwóm stanom klasycznego bitu, czyli $ 0 $ i $ 1 $ . Standardową Konwencją jest wybór

$$0 \equiv \begin{bmatrix} 1 \\\\ \end{bmatrix} , \qquad 1 \equiv \begin{bmatrix} 0 \\\\ \end{bmatrix} ,$$

Chociaż przeciwny wybór może być równie dobrze zajęty. Z tego względu nieograniczoną liczbę możliwych wektorów dwuqubitowych w stanie Quantum, tylko dwa odpowiadają stanom klasycznych bitów; wszystkie inne Stany Quantum nie są.

## <a name="measuring-a-qubit"></a>Mierzenie elementu qubit

Teraz, gdy wiemy, jak reprezentować qubit, możemy uzyskać część Intuition dla tego, co reprezentuje te Stany, omawiając koncepcję [*pomiaru*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Pomiar odnosi się do nieformalnego pomysłu "Szukaj" w qubit, który natychmiast zwija stan Quantum do jednego z dwóch stanów klasycznych $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ lub $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Po przemierzeniu qubita przez wektor stanu Quantum otrzymujemy $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ wynik $ 0 $ z prawdopodobieństwem $ | \alpha | ^ 2 $ i wynikiem $ 1 $ z prawdopodobieństwem $ | \beta | ^ 2 $ .   W wyniku $ 0 $ nowy stan qubit to $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ; w wyniku $ 1 $ jego stan wynosi $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Należy zauważyć, że te prawdopodobieństwa są sumowane do $ 1 ze $ względu na warunek normalizacji $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Właściwości pomiaru oznaczają również, że ogólny znak wektora stanu Quantum jest nieistotny. Negacja wektora jest równoznaczna z strzałką $ \alpha \right \alpha $ i $ \beta \right strzałką \beta $ . Ponieważ prawdopodobieństwo mierzenia wartości $ 0 $ i $ 1 zależy od $ wielkości kwadratowej warunków, wstawianie takich znaków nie powoduje zmiany prawdopodobieństwa. Takie fazy są zwykle nazywane [ `` *globalnymi fazami*""](https://en.wikipedia.org/wiki/Phase_factor) i bardziej ogólnie mogą mieć postać $ e ^, { \phi } $ a nie tylko $ \Pm 1 $ .

Ostateczną istotną właściwością miary jest to, że nie musi to spowodować uszkodzenia wszystkich wektorów stanu Quantum. Jeśli zaczniemy od qubit w stanie $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ , który odnosi się do stanu klasycznego $ 0 $ , zmierzenie tego stanu zawsze zwróci wynik $ 0 $ i pozostaw stan Quantum niezmieniony. W tym sensie, jeśli mamy tylko klasyczne bity (tj. qubits o wartości $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ lub $ \begin{bmatrix} 0 \\\\ 1), \end{bmatrix} $ wówczas pomiar nie uszkodzi systemu. Oznacza to, że możemy replikować klasyczne dane i manipulować nimi na komputerze z systemem Quantum, tak jak można to zrobić na klasycznym komputerze. Jednak możliwość przechowywania informacji w obu Stanach jednocześnie jest podwyższana, co jest możliwe, aby w sposób klasyczny i bardziej ROBS komputery z systemem Quantum mogły kopiować dane Quantum w nieznacznie widoczny sposób, zobacz również [theorem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Wizualizacja Qubits i transformacji przy użyciu sfery Bloch

Qubits może również być postawiony w $ 3 $ D przy użyciu reprezentacji [*sfery Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  Sfera Blocha pozwala na opisywanie jednowymiarowej, jednokierunkowej, złożonej wektora, jako trójwymiarowej wartości wektorowej.  Jest to ważne, ponieważ pozwala nam na wizualizację jednoqubitowych Stanów, a tym samym opracowywanie przyczyn, które mogą być niecenne w zrozumieniu Stanów wieloqubitowych (gdzie niestety reprezentacje Bloch Sphere nie działa).  Sfera Bloch można wizualizować w następujący sposób:

<!--- ![](.\media\bloch.svg) { Szerokość = 50%} --->
![Bloch sfera](~/media/concepts_bloch.png)

Strzałki na tym diagramie pokazują kierunek, w którym wektor stanu Quantum jest wskazywany, a każda transformacja strzałki może być uważana za rotację na jednej z osi kardynalnych.
Chociaż zastanawiasz się, że obliczenia Quantum są rozbudowane Intuition, trudne jest użycie tego Intuition do projektowania i opisywania algorytmów. Q# eliminuje ten problem, dostarczając język do opisywania rotacji.

## <a name="single-qubit-operations"></a>Operacje pojedynczej qubit

Komputery Quantum przetwarzają dane przez zastosowanie uniwersalnego zestawu bram Quantum, które mogą emulować każdy obrót wektora stanu Quantum.
To pojęcie uniwersalności jest zbliżone na potrzeby uniwersalności dla tradycyjnych (tj. klasycznych) obliczeń, w których zestaw bram jest uznawany za uniwersalny, jeśli każda transformacja bitów wejściowych może zostać wykonana przy użyciu obwodu o skończonej długości.
W przypadku przetwarzania Quantum prawidłowe przekształcenia, które możemy wykonywać na qubit są transformacje jednostkowe i pomiary.
*Podległych operacja* lub złożona sprzężona transformacja ma decydujące znaczenie dla przetwarzania Quantum, ponieważ jest to konieczne do odwrócenia transformacji Quantum.
Q# odzwierciedla to, dostarczając metody do automatycznego kompilowania sekwencji bram do ich sąsiadujących, co sprawia, że programista chce, aby adjoints kod w wielu przypadkach. Poniżej przedstawiono przykład:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Chociaż jest to prosty przykład (ponieważ < operacja linki XREF: Microsoft. Quantum. wewnętrzna. h > jest samodzielna), można zobaczyć, w jaki sposób ten stan stanie się niecenny w przypadku bardziej skomplikowanych operacji qubit.
Aby uzyskać więcej informacji, zobacz [operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions).

Istnieje tylko cztery funkcje, które mapują jeden bit na jeden bit na klasycznym komputerze. W przeciwieństwie do jednego qubit na komputerze Quantum istnieje nieskończona liczba transformacji jednostkowych. W związku z tym nie ma skończonego zestawu podstawowych operacji Quantum, nazywane [*bramami*](https://en.wikipedia.org/wiki/Quantum_logic_gate), może dokładnie replikować nieskończony zestaw przekształceń jednostkowych dozwolony w przypadku przetwarzania Quantum. Oznacza to, że w przeciwieństwie do klasycznych obliczeń nie jest możliwe, aby komputer Quantum mógł zaimplementować każdy możliwy program Quantum dokładnie przy użyciu skończonej liczby bram. Tym samym komputery Quantum nie mogą być uniwersalne w tym samym sensie klasycznych komputerów. W związku z tym, że zestaw bram jest *uniwersalny* na potrzeby przetwarzania w ramach usługi Quantum, firma Microsoft znaczy nieco słabo słabsze niż w przypadku klasycznego przetwarzania danych.
W celu zapewnienia uniwersalnego wymaga się, aby komputer Quantum był *przybliżony* tylko dla każdej macierzy jednostkowej w ramach skończonego błędu przy użyciu sekwencji bramy o skończonej długości.
Innymi słowy, zestaw bram jest uniwersalnym zestawem bram, jeśli jakakolwiek transformacja jednostkowa może być w przybliżeniu zapisywana jako iloczyn bram z tego zestawu. Wymagane jest, aby dla dowolnego z określonych błędów istniały bramy $ G_ { 1 } , G_ { 2 } , \ldots, G_N $ z zestawu bram, tak że

$$
G_N G_ { N-1 } \cdots G_2 G_1 \approx U. $$

Należy zauważyć, że ze względu na to, że Konwencja do mnożenia macierzy ma być mnożona od prawej do lewej strony pierwszej bramy w tej sekwencji, $ G_N $ , jest faktycznie ostatnią zastosowana do wektora stanu Quantum. Bardziej formalnie Załóżmy, że taki zestaw bram jest uniwersalny, jeśli dla każdej tolerancji błędów $ \epsilon > 0 $ istnieje $ G_1, \ldots G_N, $ że odległość między $ G_N \ldots G_1 $ i $ U $ jest najwyżej $ \epsilon $ . Najlepiej, aby wartość $ N $ wymagana do osiągnięcia tej odległości $ \epsilon $ powinna mieć skalę Poly-logarithmically z $ 1/\ Epsilon $ .

Co to jest uniwersalny zestaw bram, który wygląda jak w przypadku?  Najprostsza taka Uniwersalna brama na bramach qubit składa się tylko z dwóch bram: Brama Hadamard $ H $ i tak zwana $ T $ -brama (znana także jako $ brama \ pi/8 $ ):

$$
H = \frac { 1 2 1 1 } { \sqrt { } } \begin{bmatrix} & \\\\ & – 1 \end{bmatrix} , \qquad T = \begin{bmatrix} 1 0 0 & \\\\ & e ^ { i \ Pi/4 } \end{bmatrix} .
$$

Jednak ze względu na praktyczne powody dotyczące korekcji błędów Quantum może być wygodniejszy do uwzględnienia większego zestawu bram, czyli takiego, który można wygenerować przy użyciu $ H $ i $ T $ . Można sklasyfikować bramy Quantum na dwie kategorie: bramy Clifford i $ T $ -bramę.
Ten podział jest przydatny, ponieważ w wielu schematach korekcji błędów Quantum tak zwane bramy Clifford są łatwe do zaimplementowania, które wymagają bardzo kilku zasobów w zakresie operacji i qubits, aby zapewnić odporność na uszkodzenia, a bramy nieCliffordowe są dość kosztowne przy wymaganiu odporności na uszkodzenia. Standardowy zestaw bram Clifford z pojedynczą qubitą [uwzględnionych domyślnie w Q# ](xref:microsoft.quantum.libraries.standard.prelude), obejmuje

$$
H = \frac { 1 2 1 1 } { \sqrt { } } \begin{bmatrix} & \\\\ & – 1 \end{bmatrix} , \qquad S = \begin{bmatrix} 1 0 0 & \\\\ & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H,$$

$$
Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} = t ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} = T ^ 4.
$$

W tym miejscu operacje $ X $ , $ Y $ i $ Z $ są używane szczególnie często i są nazwanymi [*operatorami Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) po ich twórcy Wolfgang Pauli.
Wraz z bramą nieCliffordową ( $ T $ -bramą) te operacje mogą być składane, aby przybliżyć każdą transformację jednostkową na pojedynczym qubite.

Aby uzyskać więcej informacji na temat tych operacji, ich reprezentacje i implementacje sfery Bloch Q# , zobacz temat [operacje i funkcje wewnętrzne](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Przykładem sposobu, w jaki można kompilować przekształcenia jednostkowe z tych elementów pierwotnych, trzy przekształcenia przedstawione powyżej w sferach Bloch odpowiadają sekwencji bramy $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ 1 \end{bmatrix} $ .

Mimo że poprzednie tworzą najpopularniejsze bramy pierwotne do opisywania operacji na poziomie logicznym stosu (należy traktować poziom logiczny jako poziom algorytmu Quantum), często warto rozważyć mniejsze podstawowe operacje na poziomie algorytmu, na przykład operacje bliżej poziomu opisu funkcji. Na szczęście Q# dostępne są również metody implementowania unitaries wyższego poziomu, które z kolei umożliwiają implementowanie algorytmów wysokiego poziomu bez jawnego tworzenia wszystkiego w dół do Clifford i $ T $ -bram.

Najprostsza taka pierwotna to qubit. Trzy rotacje pojedynczej qubit są zwykle uznawane za: $ R_x $ , $ R_y $ i $ R_z $ . Aby wizualizować akcję R_x rotacji $ (\theta) $ , na przykład Wyobraź sobie, że znajduje się prawy kciuk wzdłuż kierunku $ $ osi x sfery Bloch i obracania wektora z ręką przez kąt od $ \ teta/2 $ radianów. Ten mylący współczynnik $ 2 $ wynika z faktu, że wartości wektorów ortogonalnych są równe $ 180 ^ \circ $ , gdy są wykreślane w sferze Bloch, ale faktycznie $ 90 ^ \circ $ stopni niezależnie od siebie. Odpowiednie macierze jednostkowe są następujące:

\begin{Wyrównaj* } 
 & R_z (\theta) = e ^ { -i\theta z/2 } = \begin{bmatrix} e ^ { -i \ teta/2 } & 0 \\\\ 0 & e ^ { i \ teta/2 } \end{bmatrix} , \\\\ 
 & R_x (\theta) = e ^ { -i\theta x/2 } = HR_z (\theta) H = \begin{bmatrix} \cos (\ teta/2) & -i\sin (\ teta/2) \\\\ -i\sin (\ teta/2) & \cos (\ teta/2) \end{bmatrix} , \\\\ 
 & R_y (\theta) = e ^ { -i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{bmatrix} \cos (\ teta/2) & -\sin (\ teta/2) \\\\ \sin (\ teta/2) & \cos (\ teta/2) \end{bmatrix} . \end { Wyrównaj*}

Podobnie jak każde trzy obroty mogą być połączone ze sobą w celu przeprowadzenia dowolnego obrotu w trzech wymiarach, może być widoczne z reprezentacji sfery Bloch, że każda macierz jednostkowa może być zapisywana jako sekwencja trzech rotacji. W odniesieniu do każdej macierzy jednostkowej $ u istnieje,, $ $ \alpha \beta \gamma ,, \delta $ tak że $ u = e ^ { i \alpha } R_x () \beta R_z ( \gamma ) R_x () \delta $ . W związku z tym $ R_z (\theta) $ i $ H $ tworzą także uniwersalny zestaw bram, chociaż nie jest to zestaw dyskretny, ponieważ $ \theta $ może przyjmować dowolną wartość. Z tego powodu i ze względu na aplikacje w symulacji Quantum, takie ciągłe bramy są kluczowe dla obliczeń Quantum, szczególnie na poziomie projektowania algorytmu Quantum. Aby osiągnąć implementację sprzętu odpornego na błędy, ostatecznie zostaną one skompilowane do odrębnych sekwencji bram, które ściśle przybliżą te rotacje.
