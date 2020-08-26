---
title: Paulis Description: informacje na temat pracy z operacjami pomiaru pojedynczego i wieloqubitowego Pauli.
Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Pauli MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:
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

# <a name="pauli-measurements"></a>Pomiary Pauli

W poprzednich dyskusjach koncentrujemy się na obliczaniu pomiarów bazowych.
W rzeczywistości istnieją inne typowe pomiary związane z przetwarzaniem jednostek Quantum, które z perspektywy notacji są wygodne do wyrażania na podstawie obliczeniowych pomiarów.
Podczas pracy z programem Q# najbardziej typowym rodzajem pomiarów, w których będziesz korzystać, będzie prawdopodobnie *Pauli pomiary*, które uogólnią pomiary bazowe, aby uwzględnić pomiary w innych bazach i o parzystości między różnymi qubits.
W takich przypadkach często omawia się pomiar pomiaru operatora Pauli, w ogólności operatora, takiego jak $ X, Y, Z $ lub $ z \otimes z, x \otimes x, x \otimes Y $ i tak dalej.

> [!TIP]
> W programie Q# Operatory qubit Pauli są ogólnie reprezentowane przez tablice typu `Pauli[]` .
> Na przykład, aby reprezentować $ X \otimes Z \otimes Y $ , można użyć tablicy `[PauliX, PauliZ, PauliY]` .

Omawianie pomiaru w warunkach operatorów Pauli jest szczególnie powszechne w podpolu korekcji błędów Quantum.
W programie Q# przestrzegamy podobnej Konwencji. teraz wyjaśnimy ten alternatywny widok pomiarów.

Przed napisaniem szczegółowych informacji o tym, jak sądzisz o pomiarze Pauli, warto zastanowić się nad tym, co mierzy jeden qubit wewnątrz komputera Quantum w stanie Quantum.
Wyobraź sobie, że mamy $ $ stan qubit Quantum, a następnie przemierzenie jednego qubit natychmiast $ $ wystawia 2 ^ n możliwości, które mogą znajdować się w stanie.
Innymi słowy, pomiar projektuje stan Quantum na jedną z dwóch miejsc.
Możemy uogólnić sposób, w jaki myślimy o pomiarach, aby odzwierciedlić ten Intuition.

Aby zwięzłie zidentyfikować te podobszary, należy zapoznać się z językiem.
Jednym ze sposobów opisywania dwóch podobszarów jest określenie ich za pośrednictwem macierzy, która ma dwie unikalne eigenvalues, podejmowane przez Konwencję do $ \Pm 1 $ .
Aby zapoznać się z prostym przykładem opisywania podobszarów w ten sposób, weź pod uwagę $ $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ & -1 \end{bmatrix} .
\end{align}
$$

Odczytując elementy ukośne macierzy Pauli- $ Z $ , zobaczymy, że $ z $ ma dwa eigenvectors, $ \ket { 0 } $ i $ \ket { 1 } $ , z odpowiednimi eigenvalues $ \Pm 1 $ .
W takim przypadku, jeśli mierzę qubit i uzyskamy wartość `Zero` (odpowiadającą stanowi $ \ket { 0 } $ ), wiemy, że stan naszego qubitu to $ + 1 $ eigenstate $ $ operatora z.
Podobnie, jeśli uzyskamy `One` , wiemy, że stan naszego qubit to $ -1 $ eigenstate z $ $ . Ten proces jest określany w języku Pauli pomiarów jako "pomiar Pauli $ Z $ i" jest całkowicie równoważny do wykonywania obliczeń bazowych.

Każda $ 2 \times 2 $ macierz, która jest przekształceniem jednostkowym z $ z $ również spełnia te kryteria.
Oznacza to, że możemy również użyć macierzy $ a = u ^ \dagger z u $ , gdzie $ u $ jest dowolną inną macierzą jednostkową, aby uzyskać macierz, która definiuje dwa wyniki pomiaru w $ \Pm 1 $ eigenvectors.
Notacja Pauliu odwołuje się do tej równoważności jednostki, identyfikując wartości $ X, Y, z, $ jako równoważne pomiary, które można wykonać, aby uzyskać informacje z qubit.
Te pomiary są podane poniżej dla wygody.


|Przekształcenie  | jednostek miary Pauli  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ T | $HS ^               {\dagger}$         |

Oznacza to, że przy użyciu tego języka "pomiar $ Y $ " jest odpowiednikiem zastosowania $ HS ^ \dagger $ , a następnie mierzenia w oparciu o obliczenia, gdzie [`S`](xref:microsoft.quantum.intrinsic.s) jest wewnętrzną operacją Quantum czasami nazywaną "bramą fazowy" i może być symulowana przez macierz jednostkową

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ & i \end{bmatrix} .
\end{align}
$$

Jest również odpowiednikiem zastosowania $ HS ^ \dagger $ do wektora stanu Quantum, a następnie mierzenia $ z $ , tak że Następująca operacja jest równoważna z `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Prawidłowy stan można znaleźć w wyniku przekształcenia z powrotem do podstawy obliczeniowej, co oznacza, $ że zastosowanie SH $ do wektora stanu Quantum; w powyższym fragmencie kodu przekształcenie z powrotem do podstawy obliczeniowej jest obsługiwane automatycznie przez użycie `within … apply` bloku.

W programie Q# Załóżmy, że wyniki---, czyli klasyczne informacje wyodrębnione ze stanu współdziałania ze stanem---są podawane przez `Result` wartość $ j \in \\ { \texttt { zero } , \texttt { jeden wskazuje, } \\ } $ czy wynik jest w $ (-1) ^ j $ eigenspace operatora Pauli.


## <a name="multiple-qubit-measurements"></a>Pomiary z wieloma qubitami

Pomiary operatorów Pauli wieloqubitowych są zdefiniowane w podobny sposób, jak pokazano w:

$$
Z \otimes z 1 1,0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.
$$

W ten sposób produkty dwuetapowe z dwóch $ operatorów Pauli-Z $ tworzą macierz składającą się z dwóch spacji składających się z $ + 1 $ i $ -1 $ eigenvalues.
Podobnie jak w przypadku pojedynczej qubit, oba stanowią pół obszaru, co połowa dostępnego miejsca wektorowego należy do $ + 1 $ eigenspace i pozostałe połowy do $ -1 $ eigenspace.
Ogólnie rzecz biorąc, można łatwo zapoznać się z definicją iloczynu dwuczęściowego, któremu każdy dwuczęściowy iloczyn $ operatorów Pauli-z $ i tożsamość również przestrzega tego.
Przykład:

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 &\\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 & & -1 \end{bmatrix} .
\end{align}
$$

Tak jak wcześniej, każda jednostkowa transformacja takich macierzy również opisuje dwie spacje oznaczone przez $ \Pm 1 $ eigenvalues.
Na przykład $ x \otimes x = h \otimes h (z \otimes z) h h \otimes $  od tożsamości z $ = HXH $ .
Podobnie jak w przypadku pojedynczej qubit, wszystkie dwie qubit Pauli-pomiary mogą być zapisywane jako $ u ^ \dagger (Z \otimes \id ) u $ dla $ 4 \times 4 $ macierzy jednostkowych $ U $ . Wyliczmy przekształcenia w poniższej tabeli.

> [!NOTE]
>W poniższej tabeli użyto $ \operatorname { zamiany } $ do wskazania macierzy >$$
> \begin{align}
>     \operatorname{Zamień } &=
>     \left( \begin { macierz}
>1 & 0 & 0 &\\\\
>0 & 0 & 1 &\\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & z & 1 > \end { macierzy } \right ) >     \end{align}
> $$
> służy do symulowania operacji wewnętrznej [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Przekształcenie     | jednostek miary Pauli  |
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone T $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes Z $ | $ \operatorname { wymiany } Z $|
|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { Zamień } $|
|$\boldone \otimes t $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { swap } $|
|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|
|$T \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$T \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes T $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$T \otimes T $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

W tym miejscu [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operacja zostanie wyświetlona z następującej przyczyny.
Każda miara Pauli, która nie obejmuje macierzy, jest równoważna z jednostką z z z z z $ \boldone $ $ \otimes $ powyższym powodem.
Eigenvalues z z z z z i $ \otimes $ zależą od parzystości qubits, która składa się z każdego wektora obliczeniowego, a operacje kontrolowane nie służą do obliczenia tej parzystości i zapisania jej w pierwszym bitach.
Następnie po przemierzeniu pierwszego bitu możemy odzyskać tożsamość wynikowego, który jest równoważny do mierzenia operatora Pauli.

Jedna dodatkowa Uwaga: Chociaż może być skłonny do założenia, że pomiary $ z \otimes z z $ są takie same jak pomiary $ z \otimes \mathbb { 1 } $ i 1 $ \mathbb { } \otimes z $ , to założenie będzie miało wartość false.
Powodem jest to, że pomiar z projektów z z z $ \otimes $ jest stanem Quantum do $ $ eigenstate tych operatorów + 1 lub $ -1 $ .
Pomiar $ z \otimes \mathbb { 1 } $ , a następnie $ \mathbb { 1 } \otimes z $ projektów w wektorze stanu Quantum najpierw do połowy miejsca z 1 $ \otimes \mathbb { } $ , a następnie do połowy miejsca $ \mathbb { 1 } \otimes z $ . Ponieważ istnieją cztery wektory obliczeniowe, przeprowadzenie obydwu pomiarów zmniejsza stan do kwartału, a tym samym redukuje go do jednego wektora obliczanego na podstawie.

## <a name="correlations-between-qubits"></a>Korelacje między qubits
Innym sposobem na pomiar iloczynów ilościowych macierzy Pauli, takich jak $ x \otimes x $ lub $ z \otimes z $ , jest to, że pomiary umożliwiają przeszukanie informacji przechowywanych w korelacji między tymi dwoma qubits.
Pomiar $ X \otimes \id $ pozwala przeglądać informacje, które są przechowywane lokalnie w pierwszej qubit.
Mimo że oba typy pomiarów są równie cenne w przypadku obliczeń opartych na usługach Quantum
Wykaże, że w ramach przetwarzania Quantum, często informacje, które chcesz poznać nie są przechowywane w żadnym z pojedynczych qubitów, ale raczej są przechowywane nielokalnie we wszystkich qubitsach i dlatego tylko przez ich przechodzenie przez wspólne pomiary (np. $ z \otimes $ ) czy te informacje stają się manifestem.

Na przykład w przypadku korekcji błędów często chcemy dowiedzieć się, jaki błąd wystąpił podczas uczenia niczego o stanie, który próbujesz chronić.
[Przykładowy kod przerzucania bitów](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) pokazuje przykład sposobu, w jaki można to zrobić przy użyciu pomiarów, takich jak z z i z z $ \otimes \otimes \id $ $ \id \otimes \otimes $ . < ! --Do zrobienia: Zmień tę wartość na link do przeglądarki przykładów, gdy tylko próbka kodu przerzucania bitów jest włączona. -->

Można również mierzyć dowolne operatory Pauli, takie jak $ X \otimes Y \otimes Z \otimes \boldone $ .
Wszystkie te produkty dwubajtowe operatorów Pauli mają tylko dwa eigenvalues $ \Pm 1 $ i oba eigenspaces stanowią pół miejsca całego obszaru wektora.
W ten sposób są one zgodne z wymaganiami określonymi powyżej.

W Q# , takie pomiary zwracają $ wartość j, $ Jeśli pomiar daje wynik w eigenspace znaku $ (-1) ^ j $ .
Pauli pomiary jako wbudowaną funkcję w programie Q# są przydatne, ponieważ pomiary takich operatorów wymagają długich łańcuchów kontrolowanych bram, a przekształcenia podstawowe, aby opisać bramę diagonalizing U, która jest $ $ wymagana do realizacji operacji jako iloczyn dwuskładnikowy z $ $ i $ \id $ .
Aby określić, że chcesz wykonać jedną z tych wstępnie zdefiniowanych pomiarów, nie musisz martwić się o to, jak przekształcić swoją podstawę, tak aby pomiar bazowy obliczał informacje.
Q# obsługuje automatycznie wszystkie wymagane przekształcenia podstawowe.
Aby uzyskać więcej informacji, zobacz [`Measure`](xref:microsoft.quantum.intrinsic.measure) i [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operacje.

## <a name="the-no-cloning-theorem"></a>Theorem bez klonowania

Informacje o Quantum są zaawansowane.
Umożliwia nam wykonywanie niezwykłych rzeczy, takich jak liczba czynników, które są wykładniczo szybsze niż najlepsze znane klasyczne algorytmy, lub efektywnie symuluje skorelowane systemy elektronów, które w sposób klasyczny wymagają wykładniczego kosztu, aby symulować dokładne symulacje.
Istnieją jednak ograniczenia dotyczące mocy obliczeniowej Quantum.
Takie ograniczenie jest określone przez *theorem bez klonowania*.

Theorem No-kloning ma nazwę aptly.
Nie zezwala na klonowanie ogólnych Stanów Quantum przez komputer Quantum.
Potwierdzenie theorem jest niezwykle proste.
Gdy Pełna weryfikacja theorem nie jest w stanie nieco zbyt technicznym w naszej dyskusji, w przypadku braku dodatkowych qubits pomocniczych znajduje się w naszym zakresie (pomocnicze qubits to qubits używany do wyznaczania miejsca podczas obliczeń i są łatwe w użyciu i zarządzane w programie Q# ). [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)

W przypadku takiego komputera z systemem Quantum Operacja klonowania musi być opisana przez macierz jednostkową.
Nie można wymusić pomiaru, ponieważ spowodowałoby to uszkodzenie stanu Quantum, który próbujemy sklonować.
Aby symulować operację klonowania, chcemy, aby macierz jednostkowa używała właściwości, która $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
dla każdego stanu $ \ket { \psi } $ .
Właściwość liniowości mnożenia macierzy wskazuje, że dla każdego drugiego stanu Quantum $ \ket { \phi } $ ,

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Zapewnia to podstawowe Intuition za theorem bez klonowania: każde urządzenie, które kopiuje nieznany stan Quantum, musi powodować błędy w co najmniej niektórych stanach, które kopiuje.
Podczas gdy klucz założono, że Cloner działa liniowo na stanie wprowadzania, może zostać naruszony poprzez dodanie i pomiar pomocniczej qubits, takie interakcje także przecieki informacji o systemie za pomocą statystyk pomiarów i zapobiegania dokładnemu klonowi w takich przypadkach.
Aby uzyskać bardziej szczegółowe informacje, zobacz theorem No-kloning, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).

Theorema bez klonowania jest ważna w przypadku jakościowej interpretacji obliczeń opartych na usłudze Quantum, ponieważ w przypadku niedrogiego klonowania Stanów Quantum można udzielić prawie magicalej możliwości uczenia się od Stanów Quantum.
Rzeczywiście można naruszyć zasadę niepewności vaunted Heisenberg.
Alternatywnie można użyć optymalnej Cloner do pobrania pojedynczego przykładu ze złożonej dystrybucji Quantum i dowiedzieć się wszystkiego, co może być możliwe, aby poznać tę dystrybucję z zaledwie jednego przykładu.
Przypomina to Przerzucanie monet i obserwowanie głowic, a następnie na poinformowanie przyjaciela o wyniku odpowiedzi na "Ah" dystrybucja tej monety musi być Bernoulliego z $ p = 0.512643 \ ldots $ ! "  Taka instrukcja byłaby niesensicala, ponieważ jeden bit informacji (wynik Head) po prostu nie może udostępnić wielu bitów informacji potrzebnych do zakodowania dystrybucji bez poważnych informacji.
Podobnie, bez wcześniejszej informacji, nie możemy idealnie sklonować stanu Quantum, tak samo, jak nie można przygotować kompletu takich monet bez znajomości $ p $ .

Informacje nie są bezpłatne w obliczeniach Quantum.
Każda qubit mierzona w postaci pojedynczej informacji, a theorem bez klonowania nie wykazuje, że nie ma tylne wejście, które mogą być wykorzystywane w celu założenia zasadniczego kompromisu między informacjami uzyskanymi na temat systemu a zaistniałymi zakłóceniami.
