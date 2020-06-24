---
title: Wektory i macierze w obliczeniach kwantowych
description: Poznaj podstawy pracy z wektorami i macierzami.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269545"
---
# <a name="vectors-and-matrices"></a>Wektory i macierze

Znajomość wektorów i macierzy jest niezbędna do zrozumienia przetwarzania Quantum. Udostępniamy krótkie wprowadzenie poniżej, a zainteresowani czytelnicy są zalecani do odczytania standardowego odwołania do algebry liniowego *, takiego jak Strang, G. (1993). Wprowadzenie do liniowej algebry (obj. 3). Wellesley, MA: Wellesley-Cambridge naciśnij* lub odwołanie online, takie jak [liniowe algebry](http://joshua.smcvt.edu/linearalgebra/).

Wektor kolumny (lub po prostu [*wektor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ wymiaru (lub rozmiaru) $n $ jest kolekcją $n $ liczb zespolonych $ (v_1, v_2, \ldots, v_n) $ ułożone jako kolumna:

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

Norma $v wektora $ jest definiowana jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $. Wektor jest określany jako wartość normy jednostkowej (lub alternatywnie jest nazywany [*wektorem jednostki*](https://en.wikipedia.org/wiki/Unit_vector)), jeśli jego normą jest $1 $ . [*Sąsiadująca $v wektora*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ jest oznaczona $v ^ \dagger $ i jest zdefiniowana jako wektor wiersza, gdzie $ \* $ oznacza złożony sprzężony,

$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ * & \cdots & v_n ^ * \end{bmatrix}$$

Najbardziej typowym sposobem mnożenia dwóch wektorów jest użycie [*wewnętrznego produktu*](https://en.wikipedia.org/wiki/Inner_product_space), znanego również jako iloczyn kropki.  Wewnętrzny produkt daje rzutowanie jednego wektora na inny i jest niecenny w opisie, jak wyznaczać jeden wektor jako sumę innych łatwiejszych wektorów.  Wewnętrzny produkt między $u $ i $v $ , oznaczany $ \left \langle u, v \right \rangle $ jest zdefiniowany jako

$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Ten zapis umożliwia także zapisanie normy $v wektora $ jako $ \sqrt { \langle v, v \rangle } $.

Możemy pomnożyć wektor z liczbą $c $ , aby utworzyć nowy wektor, którego wpisy są mnożone przez $c $ . Możemy również dodać dwa wektory $u $ i $v, $ Aby utworzyć nowy wektor, którego wpisy są sumą wpisów $u $ i $v $ . Poniżej przedstawiono następujące operacje:

$ $ \mathrm{If } ~ = \begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{ bmatrix } .
$$

[*Macierz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) rozmiaru $m \times n $ to zbiór $MN $ liczby zespolone uporządkowane w $m $ wiersze i $n $ kolumny, jak pokazano poniżej:

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\
M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $

Należy zauważyć, że wektor wymiaru $n $ jest po prostu macierzy rozmiaru $n \times 1 $ . Podobnie jak w przypadku wektorów możemy pomnożyć macierz z liczbą $c, $ Aby uzyskać nową macierz, w której każdy wpis jest mnożony przez $c $ , i możemy dodać dwie macierze o tym samym rozmiarze, aby utworzyć nową macierz, której wpisy są sumą odpowiednich wpisów dwóch macierzy. 

## <a name="matrix-multiplication-and-tensor-products"></a>Iloczyny i wielokrotność macierzy

Możemy również pomnożyć dwie macierze $M $ wymiar $m \times n $ i $N $ wymiar $n \times p $ w celu uzyskania nowej macierzy $P $ wymiarów $m \times p $ w następujący sposób:

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\
    M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN}
punktówbmatrix}
zacznąbmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ { } \\ \\ data\ddots\\\\
N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {np}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ p_ {12 } ~ ~ \cdots ~ ~ p_ {1p } \\ \\ p_ {21 } ~ ~ p_ {22 } ~ ~ \cdots ~ ~ p_ { } \\ \\ data\ddots\\\\
P_ {M1 } ~ ~ p_ {m2 } ~ ~ \cdots ~ ~ p_ {MP}
punktówbmatrix}
\end{align}

miejsce, w którym wpisy $P $ są $P _ {IK } = \ sum_j m_ {ij} N_ {JK } $. Na przykład wpis $P _ {11 } $ jest wewnętrznym produktem pierwszego wiersza $M $ z pierwszą kolumną $N $ . Należy zauważyć, że ponieważ wektor jest po prostu szczególnym przypadkiem macierzy, ta definicja rozciąga się na liczebność wektora. 

Wszystkie używane macierze będą macierzami kwadratowymi, gdzie liczba wierszy i kolumn jest równa lub wektorów, które odnoszą się tylko do $1 $ kolumn. Jedna specjalna macierz kwadratowa to [*macierz tożsamości*](https://en.wikipedia.org/wiki/Identity_matrix), oznaczona jako $ \boldone $ , która ma wszystkie elementy ukośne równe $1 $ i pozostałe elementy równe $0 $ :

$ $ \boldone = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \cdots ~ 0\\\\
0 ~ ~ ~ ~ \cdots ~ 0\\\\
~ ~ \ddots\\\\
0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $

W przypadku $A macierzy kwadratowej $ Załóżmy, że macierz $B $ jest jej [*odwracania*](https://en.wikipedia.org/wiki/Invertible_matrix) , jeśli $AB = ba = \boldone $ . Odwrotność macierzy nie powinna istnieć, ale gdy istnieje, jest unikatowa, a My wskazujemy ją $A ^ {-1 } $. 

W przypadku każdej $M macierzy $ , sąsiadująca lub sprzężona transtransponowana $M $ to macierz $N $ taka, która $N _ {IJ } = m_ {ji } ^ \* $. Sąsiadujące $M $ jest zwykle oznaczone $M ^ \dagger $ . Załóżmy, że macierz $U $ jest [*jednostką*](https://en.wikipedia.org/wiki/Unitary_matrix) , jeśli $uu ^ \dagger = U ^ \dagger U = \boldone $ lub równoważne, $U ^ {-1 } = U ^ \dagger $ .  Być może najważniejszym właściwością macierzy jednostkowych jest zachowanie normy wektora.  Dzieje się tak, ponieważ 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $  

$M macierzy $ jest określana jako [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , jeśli $M = M ^ \dagger $ .

Na koniec, [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (lub Kronecker produkt) dwóch macierzy $M $ rozmiaru $m \times n $ i $N $ rozmiaru $p \times q $ to większa macierz $P = M \otimes n $ rozmiaru $MP \times NQ $ i jest uzyskiwana z $M $ i $N $ w następujący sposób:

\begin{align}
    M \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\
        M_ {M1 } ~ ~ \cdots ~ ~ m_ {MN}
    punktówbmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\
        N_ {P1 } ~ ~ ~ \cdots ~ ~ N_ {pq}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } N_ {11 } ~ } \\ \\ \\\\ } } bmatrix } \\ \\ ~ \cdots ~ ~ N_ {1Q \ddots N_\\\\
        M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {MN } \begin{ bmatrix } N_ {11 } ~ } \\ \\ \\\\ } } ~ \cdots ~ ~ N_ {1Q \ddots N_bmatrix}
    \end{ bmatrix } .
\end{align}

Jest to lepsza Prezentacja z kilkoma przykładami:

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}
        \\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}
    punktówbmatrix}
    = \begin{ bmatrix } a c a a \\ \\ \\ \\ e \\ \\ b c \\ \\ \\ \\ a b d\end{bmatrix}
$$

oraz

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ g \ h \end{bmatrix}
     = \begin{bmatrix}
    z\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    Wykres\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    punktówbmatrix}
    = \begin{bmatrix}
    AE \ AF \ to \ \\ \\ DBAG \ Ah \ BG \ BH \\ \\ ce \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \end{ bmatrix } .
$$

Końcową, użyteczną Konwencją notacji otaczającą produkty dla każdego z nich, jest to, że dla dowolnego $v wektorów $ lub $M macierzy $ $v ^ {\otimes n } $ lub $M ^ {\otimes n } $ jest krótką ręką w przypadku ciągłego naliczania na $n $ .  Przykład:

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 0 &0 \\ \\&1 \\ \\ \\\\ \end{bmatrix}&0 &&1&0 &0
\end{align}
