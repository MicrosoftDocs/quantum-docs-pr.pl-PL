---
title: zaawansowane pojęcia dotyczące macierzy: informacje na temat eigenvectors, eigenvalues i wykładniczych, podstawowych narzędzi służących do opisywania i symulowania algorytmów Quantum.
Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Matrix — Advanced MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Zaawansowane koncepcje macierzy #

Teraz rozszerzamy manipulowanie macierzami na [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) i [*wykładnicze*](https://en.wikipedia.org/wiki/Matrix_exponential) , które tworzą podstawowy zestaw narzędzi potrzebnych do opisywania i implementowania algorytmów Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues i Eigenvectors ##

Przypuśćmy, $ $ że jest to macierz kwadratowa, a funkcja $ v to $ wektor, który nie jest wektorem "All Zeros" (tj. wektor ze wszystkimi wpisami równą $ 0 $ ).

Załóżmy $ $ , że v to [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ M, $ Jeśli $ = OKS $ dla pewnej liczby $ c $ . Załóżmy $ $ , że c jest [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpowiadający eigenvector $ v $ . Ogólnie rzecz biorąc $ , macierz M $ może przekształcić wektor w dowolne inne wektory, ale eigenvector jest specjalny, ponieważ pozostaje niezmieniony, z wyjątkiem tego, że jest mnożony przez liczbę. Należy pamiętać, że jeśli $ v $ jest eigenvector z eigenvalue $ c $ , to $ AV $ jest również eigenvector (dla dowolnej niezerowej $ a $ ) z tym samym eigenvalue.

Na przykład w przypadku macierzy tożsamości każdy wektor $ v $ jest eigenvector z eigenvalue $ 1 $ .

Innym przykładem jest rozważenie [*przekątnej matrycy*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D, $ która ma tylko niezerowe wpisy na przekątnej:

$$
\begin{bmatrix}
wartość d_1 & 0 & 0 0 \\\\ & d_2 & 0 0 0 \\\\ & & D_3 \end{bmatrix} .
$$

Wektory

$$\begin{bmatrix}1 \\\\ 0 \\\\ \end{bmatrix} , 0 \begin{bmatrix} \\\\ 1 \\\\ \end{bmatrix} i \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

są eigenvectors tej macierzy odpowiednio z eigenvalues $ D_1 $ , $ d_2 $ i $ D_3 $ . Jeśli $ D_1 $ , $ d_2 $ i $ D_3 $ są liczbami odrębnymi, wówczas te wektory (i ich wielokrotność) są jedyną eigenvectorsą macierzy $ d $ . Ogólnie rzecz biorąc, w przypadku matrycy ukośnej można łatwo odczytywać eigenvalues i eigenvectors. Eigenvalues są wszystkie liczby wyświetlane na przekątnej, a ich odpowiednie eigenvectors to wektory jednostek z jednym wpisem równym 1, $ $ a pozostałe wpisy są równe $ 0 $ .

Zwróć uwagę, że w powyższym przykładzie eigenvectors z $ D jest $ podstawą dla $ $ wektorów trójwymiarowych. Podstawą jest zestaw wektorów, tak że każdy wektor może być zapisany jako liniowa kombinacja. Bardziej jawnie, $ v_1 $ , $ v_2 $ i $ v_3 $ stanowią podstawę, jeśli dowolny wektor $ v $ może być zapisany jako $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ dla niektórych liczb $ A_1 $ , $ a_2 $ i $ a_3 $ .

Odwołaj, że macierz hermitian (nazywana również własnym) to złożona macierz kwadratowa równa własnej złożonej funkcji sprzężonej, a macierz jednostkowa to złożona macierz kwadratowa, której odwrotność jest równa jego przylegającej lub złożonej funkcji sprzężonej.
W przypadku hermitian i macierzy jednostkowych, które zasadniczo są jedynymi macierzami wykrytymi w ramach obliczeń opartych na usłudze Quantum, istnieje ogólny wynik, który jest znany jako [*widmo theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), które potwierdzają następujące kwestie: dla każdej Hermitianej lub macierzy jednostkowej $ M $ , istnieje jednostka a, $ $ która oznacza, że $ M = u w \dagger $ przypadku niektórych przekątnych macierzy $ D $ . Ponadto, ukośne wpisy $ D $ będą eigenvalues $ M $ .

Wiemy już, jak obliczyć eigenvalues i eigenvectorse dla macierzy ukośnych $ D $ . Korzystając z tej theorem, wiemy, że jeśli $ v $ jest eigenvectorem $ D $ z eigenvalue $ c $ , tj. $ cyfrowa = CV $ , a następnie $ U ^ \dagger v $ będzie eigenvector $ M $ z eigenvalue $ c $ . Dzieje się tak, ponieważ

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (U u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Wykładnicze macierze
W przypadku funkcji wykładniczej można również zdefiniować wartość [*wykładniczą macierzy*](https://en.wikipedia.org/wiki/Matrix_exponential) .  Wartość wykładnicza macierzy macierzy $ a $ może być wyrażona jako

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { ! } + \frac { ^ 3 } { 3!}+\cdots
$$

Jest to ważne, ponieważ zmiana czasu mechanicznego Quantum jest opisana przez macierz jednostkową formularza $ e ^ { IB } $ dla hermitian macierzy $ B $ .  Z tego powodu wykonywanie wartości wykładniczych macierzy jest podstawową częścią obliczeniowych procesów Quantum, a jako takie Q# oferują procedury wewnętrzne umożliwiające opisywanie tych operacji.
Istnieje wiele sposobów na rozliczenie matrycy wykładniczej na klasycznym komputerze i ogólnie numeryczne przybliżenie takiej wartości wykładniczej to fraught z Peril.  Zobacz [*Cleve Moler i Charles van. "Nineteen podejrzanych metody obliczeń wykładniczych macierzy". SIAM przegląd 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , aby uzyskać więcej informacji na temat wyzwań.

Najprostszym sposobem, aby zrozumieć, jak obliczyć wartość wykładniczą macierzy, za pomocą eigenvalues i eigenvectors tej macierzy.  W odniesieniu do theorem widma omówione powyżej mówi, że dla każdej hermitian lub macierzy jednostkowej $ $ istnieje macierz jednostkowa $ u $ i $ wielowarstwowa macierz D, $ taka jak $ = u \dagger $ .  Ze względu na właściwości unitarity mamy, że $ ^ 2 = u ^ \dagger d ^ 2 u $ i podobne dla każdej potęgi $ p $ $ ^ p = ^ \dagger d ^ p $ .  Jeśli ta funkcja zostanie zastąpiona definicją operatora operatora wykładniczego, uzyskujemy:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$

Innymi słowy, jeśli przekształcasz na eigenbasis macierzy a, a $ $ następnie obliczamy wartość wykładniczą macierzy, jest równoważne obliczaniu zwykłej wartości wykładniczej eigenvalues macierzy.  Ponieważ wiele operacji obliczeniowych opartych na infrastrukturze opartej na protokole Quantum obejmuje wykonywanie wartości wykładniczych macierzy, to ta część transformacji w eigenbasis macierzy, która upraszcza wykonywanie operatora wykładniczego, i jest podstawą za wiele algorytmów Quantum, takich jak Trotter – Suzuki-style metody symulacji w dalszej części tego przewodnika.

Inną przydatną właściwością jest to, że $ b $ jest zarówno jednostką, jak i hermitian, czyli $ b = b ^ { -1 } = b ^, \dagger $ a następnie $ b ^ 2 = \boldone $ . Stosując tę regułę do powyższego rozwinięcia macierzy wykładniczej i grupując $ \boldone $ $ warunki i B $ razem, można zobaczyć, że dla dowolnych wartości rzeczywistych $ x $ tożsamość

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


przechowywane. Ta lewę jest szczególnie przydatna, ponieważ umożliwia jej przyczynę o wartościach wykładniczych macierzy akcji, nawet jeśli wymiar $ b $ jest duży, w przypadku sytuacji, gdy $ b $ jest to jednostka jednostkowa i hermitian.
