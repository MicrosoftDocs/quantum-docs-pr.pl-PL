---
title: wektory i macierze w opisie przetwarzania Quantum: Poznaj podstawy pracy z wektorami i macierzami.
Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Vectors MS. Author: v-benbra MS. Date: 12/11/2017 MS. temat: koncepcyjne No-Loc:
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

# <a name="vectors-and-matrices"></a>Wektory i macierze

Znajomość wektorów i macierzy jest niezbędna do zrozumienia przetwarzania Quantum. Udostępniamy krótkie wprowadzenie poniżej, a zainteresowani czytelnicy są zalecani do odczytania standardowego odwołania do algebry liniowego *, takiego jak Strang, G. (1993). Wprowadzenie do liniowej algebry (obj. 3). Wellesley, MA: Wellesley-Cambridge naciśnij* lub odwołanie online, takie jak [algebry liniowe](http://joshua.smcvt.edu/linearalgebra/).

Wektor kolumny (lub po prostu [*wektor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ wymiaru (lub rozmiaru) $ n $ jest kolekcją $ n $ liczb zespolonych $ (v_1, v_2, \ldots, v_n) $ uporządkowanych jako kolumna:

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

Norma wektora $ v $ jest definiowana jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ . Wektor jest określany jako wartość normy jednostkowej (lub alternatywnie jest nazywany [*wektorem jednostki*](https://en.wikipedia.org/wiki/Unit_vector)), jeśli jej normą $ jest $ 1. [*Sąsiadująca wektora*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ jest oznaczona jako $ \dagger $ wektora v ^ i jest definiowana jako następująca Vector, gdzie $ \* $ wskazuje złożona sprzężona,

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

Najbardziej typowym sposobem mnożenia dwóch wektorów jest użycie [*wewnętrznego produktu*](https://en.wikipedia.org/wiki/Inner_product_space), znanego również jako iloczyn kropki.  Wewnętrzny produkt daje rzutowanie jednego wektora na inny i jest niecenny w opisie, jak wyznaczać jeden wektor jako sumę innych łatwiejszych wektorów.  Wewnętrzny produkt między $ u $ i $ v $ , oznaczany $ \left \langle u, v \right \rangle $ jest zdefiniowany jako

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Ten zapis umożliwia także zapisanie normy wektora $ v $ jako $ \sqrt { \langle v, v \rangle } $ .

Możemy pomnożyć wektor z liczbą c, $ $ Aby utworzyć nowy wektor, którego wpisy są mnożone przez $ c $ . Możemy również dodać dwa wektory $ u $ i $ v $ w celu utworzenia nowego wektora, którego wpisy są sumą wpisów $ u $ i $ v $ . Poniżej przedstawiono następujące operacje:

$$\mathrm{Jeśli } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { i}~
v =\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} , ~ \mathrm { następnie}~
Au + BV =\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n i bv_n \end{bmatrix} .
$$

[*Macierz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) o rozmiarze $ m \times n $ to zbiór $ $ liczb zespolonych MN uporządkowanych w $ $ wierszach m i $ n $ kolumn, jak pokazano poniżej:

$$Mol = 
\begin{bmatrix}
M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
\ddots\\\\
M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\
\end{bmatrix}.$$

Należy zauważyć, że wektor wymiaru $ n $ jest po prostu macierzą o rozmiarze $ n \times 1 $ . Podobnie jak w przypadku wektorów, możemy pomnożyć macierz o liczbie $ c $ , aby uzyskać nową macierz, w której każdy wpis jest mnożony przez $ c $ , i można dodać dwie macierze o tym samym rozmiarze, aby utworzyć nową macierz, której wpisy są sumą odpowiednich wpisów dwóch macierzy. 

## <a name="matrix-multiplication-and-tensor-products"></a>Iloczyny i wielokrotność macierzy

Możemy również pomnożyć dwie macierze $ m $ wymiaru $ m \times n $ i $ n $ wymiaru $ n \times p, $ Aby uzyskać nową macierz $ p $ o wymiarze $ m \times p $ w następujący sposób:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
    M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
    \ddots\\\\
    M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ {}\\\\
\ddots\\\\
N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ p_ { 12 } ~~ \cdots ~~ p_ { 1p}\\\\
P_ { 21 } ~~ p_ { 22 } ~~ \cdots ~~ p_ {}\\\\
\ddots\\\\
P_ { M1 } ~~ p_ { m2 } ~~ \cdots ~~ p_ { MP}
\end{bmatrix}
\end{align}

miejsce, w którym wpisy $ P $ są $ p_ { IK } = \sum _j M_ { IJ } N_ { JK } $ . Na przykład wpis $ p_ { 11 } $ jest wewnętrznym produktem pierwszego wiersza $ M $ z pierwszą kolumną $ N $ . Należy zauważyć, że ponieważ wektor jest po prostu szczególnym przypadkiem macierzy, ta definicja rozciąga się na liczebność wektora. 

Wszystkie używane macierze będą macierzami kwadratowymi, gdzie liczba wierszy i kolumn jest równa lub wektorów, które odnoszą się tylko do $ 1 $ kolumny. Jedna specjalna macierz kwadratowa to [*macierz tożsamości*](https://en.wikipedia.org/wiki/Identity_matrix), oznaczona $ \boldone $ , która ma wszystkie elementy ukośne równe $ 1 $ i pozostałe elementy równe $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ 0 \cdots ~~\\\\
0 ~~ 1 ~~ \cdots ~~\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ \end{bmatrix} .$$

W przypadku macierzy kwadratowej $ a firma $ Microsoft zaleca, $ Aby macierz B $ była [*odwrócona*](https://en.wikipedia.org/wiki/Invertible_matrix) , jeśli $ AB = ba = \boldone $ . Odwrotność macierzy nie może istnieć, ale gdy istnieje, jest unikatowa i oznacza to $ ^ { -1 } $ . 

Dla każdej macierzy $ m $ , sąsiadujące lub sprzężone przestawianie $ m $ to macierz N, $ $ która $ N_ { IJ } = m_ { ji } ^ \* $ . Sąsiadująco $ m $ jest zwykle oznaczona symbolem $ m ^ \dagger $ . Załóżmy, że macierz $ u $ jest [*jednostką*](https://en.wikipedia.org/wiki/Unitary_matrix) $ , jeśli uu ^ \dagger = u ^ \dagger u = \boldone $ lub równoważne, $ U ^ { -1 } = U ^ \dagger $ .  Być może najważniejszym właściwością macierzy jednostkowych jest zachowanie normy wektora.  Dzieje się tak, ponieważ 

$$\langlev, v v \rangle = ^ \dagger v = ^ \dagger u ^ { -1 } u v v = ^ \dagger u ^ u \dagger v = \langle , u v \rangle .$$  

Macierz $ m $ jest określana jako [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , jeśli $ m = m ^ \dagger $ .

Na koniec, [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (lub produkt Kronecker) dwóch macierzy $ m $ o rozmiarze $ m \times $ i $ n $ rozmiaru $ p \times q $ to większa macierz $ p = M \otimes $ o rozmiarze $ MP \times NQ i $ jest uzyskiwana z $ M $ i $ n $ w następujący sposób:

\begin{align}
    M \otimes N &=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ m_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Jest to lepsza Prezentacja z kilkoma przykładami:

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =a \begin{bmatrix} c a \\\\ d a \\\\ e \\\\ b c b \\\\ d \\\\\end{bmatrix}
$$

oraz

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d \end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h \end{bmatrix}
     =
    \begin{bmatrix}
    z\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    Wykres\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE \ AF \ nie należy \\\\
    AG \ Ah \ BG \ BH \\\\
    ce \ CF \ de \ DF \\\\
    CG \ ch \ DG \ DH \end{bmatrix} .
$$

Ostateczną, użyteczną Konwencją notacji otaczającą produkty na siebie, jest to, że dla dowolnego wektora $ v $ lub macierz $ m $ , $ v ^ { \otimes n } $ lub $ m ^ { \otimes n } $ jest krótkie dla jednostronicowego $ $ produktu dwuetapowego.  Na przykład:

\begin{align}
&\begin{bmatrix}1 0 1 0, 1 0 1, 0 0 \\\\ \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} \qquad \begin{bmatrix} \\\\ \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} -1-1-1,\\\\
  &\begin{bmatrix}0 1 1 0 1,0 1 0 & \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & \\\\ & \end{bmatrix} , \qquad \begin{bmatrix} 0 1 1,0 & \\\\ & 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1,0 0 0 0 0 0 1 0 0 0
\end{align}
