---
title: Opis platformy Quantum Oracle: informacje na temat pracy z i definiowania Quantum Oracle, operacje czarnego pola, które są używane jako dane wejściowe w innym algorytmie.
Autor: cgranade UID: Microsoft. Quantum. koncepcje. Oracles MS. Author: chgranad MS. Date: 07/11/2018 MS. temat: artykuł No-Loc:
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
# <a name="quantum-oracles"></a>Bazy danych Quantum Oracle

Oracle $ O $ to operacja "czarna Box", która jest używana jako dane wejściowe w innym algorytmie.
Często takie operacje są definiowane przy użyciu funkcji klasycznej $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m, $ która przyjmuje $ n $ -bitowe dane binarne danych binarnych i tworzy $ $ mikrobitowe dane wyjściowe binarne.
W tym celu należy wziąć pod uwagę określony kod binarny $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .
Możemy etykietować Stany qubit jako $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .

Możemy najpierw spróbować zdefiniować $ o tak, aby $ $ o \ket { x } = \ket { f (x) } $ , ale wystąpiło kilka problemów.
Po pierwsze, $ f $ może mieć inny rozmiar danych wejściowych i wyjściowych ( $ n \ne m $ ), co oznacza, że zastosowanie $ $ w programie spowoduje zmianę liczby qubits w rejestrze.
Sekunda, nawet jeśli $ n = m $ , funkcja nie może być odwracalna: Jeśli $ f (x) = f (y) $ dla niektórych $ x \ne y $ , następnie $ o \ket { x } = o \ket { y, } $ ale $ o ^ \dagger o x o ^ o \ket { } \ne \dagger \ket { y } $ .
Oznacza to, że nie będzie można skonstruować operacji sąsiedniej $ O ^ \dagger $ , a firmy Oracle muszą mieć dla nich przyległych.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe
Firma Microsoft może zająć się obydwoma problemami, wprowadzając drugi rejestr $ m $ qubits do przechowywania odpowiedzi.
Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $ x \in \\ { 0, 1 \\ } ^ n $ i $ y \in \\ { 0, 1 \\ } ^ m $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Teraz $ o = ^ \dagger $ przez konstrukcję, dlatego zostały rozwiązane oba poprzednie problemy.

> [!TIP]
>Aby zobaczyć, że o $ = godzinie "o ^" { \dagger } $ , należy pamiętać, że $ ^ 2 = \boldone $ od $ \oplus b \oplus b = a $ dla wszystkich $ a, b \in \: :: No-Loc ({)::: 0, 1 \: :: No-Loc (})::: $ .
>W związku z tym $ o \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Ważną kwestią jest zdefiniowanie Oracle w ten sposób w przypadku każdego stanu podstawy obliczeniowej $ \ket { x y, a } \ket { } $ także zdefiniowanie $ $ działań dla każdego innego stanu.
Następuje to bezpośrednio od faktu $ , że $ , podobnie jak wszystkie operacje Quantum, jest liniowy w stanie, w którym działa.
Rozważmy operację Hadamard, na przykład, która jest zdefiniowana przez $ h \ket { 0 } = \ket { + } $ i $ h \ket { 1 } = \ket { - } $ .
Jeśli chcemy dowiedzieć się $ , jak h $ działa $ \ket { + } $ , można użyć tej $ godziny $ , która jest liniowa,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

W przypadku definiowania naszej firmy Oracle $ O $ można w podobny sposób wykorzystać, że każdy stan $ \ket { \psi } $ na $ n + m $ qubits można napisać jako

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

gdzie $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ reprezentuje współczynniki stanu $ \ket { \psi } $ . Tak więc,

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Fazy Oracle
Alternatywnie możemy kodować program $ f $ do programu Oracle $ o, $ stosując _fazę_ w oparciu o dane wejściowe $ $ . Można na przykład określić, $ $ że $$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Jeśli faza Oracle działa na bieżąco z rejestrem w stanie obliczenia $ \ket { x } $ , wówczas ta faza jest globalnym etapem i dlatego nie jest zauważalna.
Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.
Rozważmy na przykład fazę $ O_f firmy Oracle $ dla funkcji pojedynczej qubit $ f $ .
Następnie $$
\begin{align}
    O_f \ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.

Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.
Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.


Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
