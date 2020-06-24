---
title: Zaawansowane pojęcia dotyczące macierzy
description: Więcej informacji na temat eigenvectors, eigenvalues i matryc wykładniczych, podstawowych narzędzi używanych do opisywania i symulowania algorytmów Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- $$
- $$
- $$
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269460"
---
# <a name="advanced-matrix-concepts"></a>Zaawansowane koncepcje macierzy #

Teraz rozszerzamy manipulowanie macierzami na [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) i [*wykładnicze*](https://en.wikipedia.org/wiki/Matrix_exponential) , które tworzą podstawowy zestaw narzędzi potrzebnych do opisywania i implementowania algorytmów Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues i Eigenvectors ##

Niech $M $ być tablicą kwadratową i $v $ być wektorem, który nie jest wektorem "All Zeros" (tj. wektor ze wszystkimi pozycjami równymi $0 $ ).

Załóżmy, że $v $ jest [*eigenvectorem*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $M, $ Jeśli $MV = CV $ dla niektórych $c liczby $ . Załóżmy, $c $ jest [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpowiadający $v eigenvector $ . Ogólnie rzecz biorąc, macierz $M $ może przekształcić wektor w inne wektory, ale eigenvector jest specjalny, ponieważ pozostanie niezmieniony, z wyjątkiem tego, że jest mnożony przez liczbę. Należy pamiętać, że jeśli $v $ jest eigenvector z eigenvalue $c $ , wówczas $AV $ jest również eigenvector (dla dowolnej niezerowej $a $ ) z tym samym eigenvalue.

Na przykład w przypadku macierzy tożsamości każda $v wektora $ jest eigenvector z eigenvalue $1 $ .

Innym przykładem jest rozważenie $D [*macierzy ukośnej*](https://en.wikipedia.org/wiki/Diagonal_matrix) , $ która ma tylko niezerowe wpisy na przekątnej:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .
$$

Wektory

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ \end{bmatrix} i \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$

są eigenvectors tej macierzy z eigenvalues $d _1 $ , $d _2 $ i $d _3 $ . Jeśli $d _1 $ , $d _2 $ i $d _3 $ to odrębne liczby, wówczas te wektory (i ich wielokrotność) są jedynymi eigenvectorsami $D macierzy $ . Ogólnie rzecz biorąc, w przypadku matrycy ukośnej można łatwo odczytywać eigenvalues i eigenvectors. Eigenvalues są wszystkie liczby wyświetlane na przekątnej, a ich odpowiednie eigenvectors to wektory jednostek z jednym wpisem równym $1, $ a pozostałe wpisy są równe $0 $ .

Zwróć uwagę, że w powyższym przykładzie eigenvectors $D $ stanowią podstawę dla $ wektorów $3. Podstawą jest zestaw wektorów, tak że każdy wektor może być zapisany jako liniowa kombinacja. Bardziej jawnie, $v _1 $ , $v _2 $ i $v _3, a $ $v wektorów $ można napisać jako $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ dla niektórych liczb $a _1 $ , $a _2 $ i $a _3 $ .

Należy przypomnieć, że macierz hermitian (nazywana również własnym) jest złożoną jednostkową tablicą równą jej własnej złożonej sprzężonej, podczas gdy macierz jednostkowa to złożona macierz kwadratowa, której odwrotność jest równa jego złożonej sprzężonej.
W przypadku hermitian i macierzy jednostkowych, które zasadniczo są jedyne macierzy spotykanych w ramach obliczeń opartych na usłudze Quantum, istnieje ogólny wynik, znany jako [*widmo theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), które potwierdzają następujące kwestie: dla każdej Hermitianowej lub $mej macierzy $ , istnieje $U, $ która $M = U ^ \dagger D u $ dla niektórych przekątnych macierzy $D $ . Ponadto, ukośne wpisy $D $ będą eigenvalues $M $ .

Wiemy już, jak obliczyć eigenvalues i eigenvectors macierzy ukośnej $D $ . Korzystając z tej theorem, wiemy, że jeśli $v $ jest eigenvector $D $ z eigenvalue $c $ , tj., $DV = CV $ , a następnie $U ^ \dagger v $ będzie eigenvector $M $ z eigenvalue $c $ . Dzieje się tak, ponieważ

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Wykładnicze macierze
W przypadku funkcji wykładniczej można również zdefiniować wartość [*wykładniczą macierzy*](https://en.wikipedia.org/wiki/Matrix_exponential) .  Wartość wykładnicza macierzy $A macierzy $ może być wyrażona jako

$ $ e ^ A = \boldone + A + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $

Jest to ważne, ponieważ zmiana czasu mechanicznego Quantum jest opisana przez macierz jednostkową formularza $e ^ {iB } $ for hermitian matrix $B $ .  Z tego powodu wykonywanie wartości wykładniczych macierzy jest podstawową częścią obliczeniowej usługi Quantum i ponieważ ten Q # oferuje procedury wewnętrzne do opisywania tych operacji.
Istnieje wiele sposobów na rozliczenie matrycy wykładniczej na klasycznym komputerze i ogólnie numeryczne przybliżenie takiej wartości wykładniczej to fraught z Peril.  Zobacz [*Cleve Moler i Charles van. "Nineteen podejrzanych metody obliczeń wykładniczych macierzy". SIAM przegląd 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , aby uzyskać więcej informacji na temat wyzwań.

Najprostszym sposobem, aby zrozumieć, jak obliczyć wartość wykładniczą macierzy, za pomocą eigenvalues i eigenvectors tej macierzy.  W odniesieniu do theorem widma opisanego powyżej mówi, że dla każdej hermitian lub macierzy jednostkowej $A $ istnieje macierz jednostkowa $U $ i matryca ukośna $D $ taka $A = U ^ \dagger D u $ .  Ze względu na właściwości unitarity, że $A ^ 2 = U ^ \dagger D ^ 2 U $ i podobne dla dowolnego $PA, $ $A ^ p = U ^ \dagger D ^ p U $ .  Jeśli ta funkcja zostanie zastąpiona definicją operatora operatora wykładniczego, uzyskujemy:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $

Innymi słowy, jeśli przekształcisz się na eigenbasis $A macierzy, $ a następnie obliczenia wykładnicze macierzy są równoważne do obliczania zwykłej wykładniczej eigenvalues macierzy.  Ponieważ wiele operacji obliczeniowych opartych na infrastrukturze opartej na protokole Quantum obejmuje wykonywanie wartości wykładniczych macierzy, to ta część transformacji w eigenbasis macierzy, która upraszcza wykonywanie operatora wykładniczego, i jest podstawą za wiele algorytmów Quantum, takich jak Trotter – Suzuki-style metody symulacji w dalszej części tego przewodnika.

Inną przydatną właściwością jest to, że $B $ jest zarówno jednostkowa, jak i hermitian, czyli $B = b ^ {-1 } = B ^ \dagger, $ a następnie $B ^ 2 = \boldone $ . Zastosowanie tej reguły do powyższego rozwinięcia macierzy wykładniczej i przez zgrupowanie wartości $ \boldone $ oraz $Bych $ warunków może być widoczne dla każdej wartości rzeczywistej $x $ tożsamości

$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $


przechowywane. Ta lewę jest szczególnie przydatna, ponieważ pozwala na to przyczynę o wartościach wykładniczych macierzy akcji, nawet jeśli wymiar $B $ jest duży, w przypadku sytuacji, gdy $B $ jest zarówno jednostkowe, jak i hermitian.
