---
title: Wektory i macierze w obliczeniach Quantum
description: Poznaj podstawy pracy z wektorami i macierzami.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 076ab6242b7ae31d4936ae8505034f1f13fa4727
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904914"
---
# <a name="vectors-and-matrices"></a>Wektory i macierze

Znajomość wektorów i macierzy jest niezbędna do zrozumienia przetwarzania Quantum. Udostępniamy krótkie wprowadzenie poniżej, a zainteresowani czytelnicy są zalecani do odczytania standardowego odwołania do algebry liniowego *, takiego jak Strang, G. (1993). Wprowadzenie do liniowej algebry (obj. 3). Wellesley, MA: Wellesley-Cambridge naciśnij* lub odwołanie online, takie jak [liniowe algebry](http://joshua.smcvt.edu/linearalgebra/).

Wektor kolumny (lub po prostu [*wektor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ wymiaru (lub rozmiaru) $n $ jest kolekcją $n $ Complex Numbers $ (v_1, v_2, \ldots, v_n) $ ułożone jako kolumna:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

Norma $v wektora $ została zdefiniowana jako $ \sqrt{\sum\_i | v\_i | ^ 2} $. Wektor jest określany jako wartość normy jednostkowej (lub alternatywnie jest nazywany [*wektorem jednostki*](https://en.wikipedia.org/wiki/Unit_vector)), jeśli jej normą jest $1 $. [*Sąsiadująco wektor*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ jest zanotowany $v ^ \dagger $ i jest zdefiniowany jako wektor wiersza, gdzie $\*$ oznacza złożony sprzężony,

$ $ \begin{bmatrix} v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

Najbardziej typowym sposobem mnożenia dwóch wektorów jest użycie [*wewnętrznego produktu*](https://en.wikipedia.org/wiki/Inner_product_space), znanego również jako iloczyn kropki.  Wewnętrzny produkt daje rzutowanie jednego wektora na inny i jest niecenny w opisie, jak wyznaczać jeden wektor jako sumę innych łatwiejszych wektorów.  Wewnętrzny produkt między $u $ i $v $, \left\langle u, v\right\rangle $ jest zdefiniowany jako

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Ten zapis umożliwia również zapisanie normy wektora $v $ jako $ \sqrt{\langle v, v\rangle} $.

Możemy pomnożyć wektor z liczbą $c $, aby utworzyć nowy wektor, którego wpisy są mnożone przez $c $. Możemy również dodać dwa wektory $u $ i $v $, aby utworzyć nowy wektor, którego wpisy są sumą wpisów $u $ i $v $. Poniżej przedstawiono następujące operacje:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 bv_2\\\\ \vdots\\\\ au_n bv_n \end{bmatrix}.
$$

[*Macierz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) rozmiaru $m \times n $ jest kolekcją $MN $ Complex Numbers uporządkowaną w $m $ rows i $n $ Columns, jak pokazano poniżej:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN}\\\\ \end{bmatrix}. $ $

Należy zauważyć, że wektor wymiaru $n $ jest po prostu macierzą rozmiaru $n \times $1. Podobnie jak w przypadku wektorów możemy pomnożyć macierz z liczbą $c $, aby uzyskać nową macierz, w której każdy wpis jest mnożony przez $c $, i możemy dodać dwie macierze o tym samym rozmiarze, aby utworzyć nową macierz, której wpisy są sumą odpowiednich wpisów dwóch macierzy. 

## <a name="matrix-multiplication-and-tensor-products"></a>Iloczyny i wielokrotność macierzy

Możemy również pomnożyć dwie macierze $M $ wymiaru $m \times n $ i $N $ wymiaru $n \times p $, aby uzyskać nową macierz $P $ wymiaru $m \times p $ w następujący sposób:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \begin{bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1p}\\\\ N_{21} ~ ~ N_{22} ~ ~ ~ ~ ~ N_ {\cdots}\\\\ \ddots\\\\ N_ {N1} ~ ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {np} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {Data}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{bmatrix} \end{align}

miejsce, w którym wpisy $P $ są $P _ {IK} = \ sum_j M_ {IJ} N_ {JK} $. Na przykład wpis $P _{11}$ jest wewnętrznym produktem pierwszego wiersza $M $ z pierwszą kolumną $N $. Należy zauważyć, że ponieważ wektor jest po prostu szczególnym przypadkiem macierzy, ta definicja rozciąga się na liczebność wektora. 

Wszystkie używane macierze będą macierzami kwadratowymi, w których liczba wierszy i kolumn jest równa lub wektorów, które odpowiadają tylko $1 $ kolumny. Jedna specjalna macierz kwadratowa to [*macierz tożsamości*](https://en.wikipedia.org/wiki/Identity_matrix), oznaczona jako $ \boldone $, która ma wszystkie jego elementy ukośne równe $1 $ i pozostałe elementy równe $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ ~ ~ ~ \cdots ~ \\\\~ ~ ~ ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

W przypadku macierzy kwadratowej $A $ Załóżmy, że macierz $B $ jest [*odwracana*](https://en.wikipedia.org/wiki/Invertible_matrix) , jeśli $AB = ba = \boldone $. Odwrotność macierzy nie powinna istnieć, ale gdy istnieje, jest unikatowa i jest ona zanotowana $A ^{-1}$. 

Dla każdej macierzy $M $, sąsiedniej lub sprzężonej transpozycji $M $ to macierz $N $, która $N _ {IJ} = M_ {ji} ^\*$. Replika $M $ jest zwykle oznaczona $M ^ \dagger $. Załóżmy, że macierz $U $ jest [*jednostką*](https://en.wikipedia.org/wiki/Unitary_matrix) , jeśli $uu ^ \Dagger = u ^ \dagger U = \boldone $ lub równoważne, $U ^{-1} = u ^ \dagger $.  Być może najważniejszym właściwością macierzy jednostkowych jest zachowanie normy wektora.  Dzieje się tak, ponieważ 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

Macierz $M $ jest określana jako [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , jeśli $M = M ^ \dagger $.

Na koniec, [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (lub Kronecker produkt) dwóch macierzy $M $ rozmiaru $m \times n $ i $N $ rozmiaru $p q $ to większa macierz $P = M\otimes n $ rozmiaru $MP \times NQ $ i jest uzyskiwana z $M $ i $N $ w następujący sposób:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ M_ {M1} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {M1} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ m_ {MN} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{ bmatrix} \end{bmatrix}.
\end{align}

Jest to lepsza Prezentacja z kilkoma przykładami:

$ $ \begin{bmatrix} \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ d \\\\ \\c \\\\ b d \\\\ be\end {bmatrix} $ $\\

i

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ to \ Data \\t_15_ AG \ Ah \ BG \ BH \\\\ ce \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{bmatrix}.\\
$$

Ostateczną użyteczną Konwencją notacji otaczającą produkty na tym samym poziomie jest to, że dla dowolnego wektora $v $ lub macierz $M $, $v ^ {\otimes n} $ lub $M ^ {\otimes n} $ jest krótka dla $nego, ciągłego rozliczania.  Na przykład:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{ bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 bmatrix}.\\\\
\end{align}
