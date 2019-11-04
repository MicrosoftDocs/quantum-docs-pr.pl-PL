---
title: Zaawansowane koncepcje dotyczące macierzy | Microsoft Docs
description: Zaawansowane koncepcje macierzy
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183764"
---
# <a name="advanced-matrix-concepts"></a>Zaawansowane koncepcje macierzy #

Teraz rozszerzamy manipulowanie macierzami na [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) i [*wykładnicze*](https://en.wikipedia.org/wiki/Matrix_exponential) , które tworzą podstawowy zestaw narzędzi potrzebnych do opisywania i implementowania algorytmów Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues i Eigenvectors ##

Niech $M $ być macierzą kwadratową, a $v $ jest wektorem, który nie jest wektorem "All Zeros" (tj. wektor ze wszystkimi pozycjami równymi $0 $).

Załóżmy, $v $ to [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $M $ if $MV = CV $ dla niektórych liczb $c $. Załóżmy, że $c $ jest [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpowiadającym eigenvector $v $. Ogólnie rzecz biorąc, macierz $M $ może przekształcić wektor w dowolne inne wektory, ale eigenvector jest specjalny, ponieważ pozostaje niezmieniony, z wyjątkiem tego, że jest mnożony przez liczbę. Należy pamiętać, że jeśli $v $ jest eigenvector z eigenvalue $c $, a następnie $av $ jest również eigenvector (dla dowolnej niezerowej $a $) z tym samym eigenvalue.

Na przykład w przypadku macierzy tożsamości każdy wektor $v $ jest eigenvector z eigenvalue $1 $.

Innym przykładem jest rozważenie $D [*macierzy ukośnej*](https://en.wikipedia.org/wiki/Diagonal_matrix) $, która ma tylko niezerowe wpisy na przekątnej:

$ $ \begin{bmatrix} D_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix}.
$$

Wektory

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ End {bmatrix} i \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ End {bmatrix} $ $

są eigenvectors tej macierzy z eigenvalues $d _1 $, $d _2 $ i $d _3 $, odpowiednio. Jeśli $d _1 $, $d _2 $, i $d _3 $ to różne liczby, wówczas te wektory (i ich wielokrotność) są jedynym eigenvectors macierzy $D $. Ogólnie rzecz biorąc, w przypadku matrycy ukośnej można łatwo odczytywać eigenvalues i eigenvectors. Eigenvalues są wszystkie liczby wyświetlane na przekątnej, a ich odpowiednie eigenvectors to wektory jednostek z jednym wpisem równym $1 $, a pozostałe wpisy równe $0 $.

Zwróć uwagę, że w powyższym przykładzie $D eigenvectors $ jest podstawą dla wektorów $3 $-wymiarowe. Podstawą jest zestaw wektorów, tak że każdy wektor może być zapisany jako liniowa kombinacja. Dokładniej, $v _1 $, $v _2 $, i $v _3 $ tworzą podstawę, jeśli dowolny wektor $v $ można napisać jako $v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ dla niektórych liczb $a _1 $, $a _2 $ i $a _3 $.

Należy przypomnieć, że macierz hermitian (nazywana również własnym) jest złożoną jednostkową tablicą równą jej własnej złożonej sprzężonej, podczas gdy macierz jednostkowa to złożona macierz kwadratowa, której odwrotność jest równa jego złożonej sprzężonej.
W przypadku hermitian i macierzy jednostkowych, które zasadniczo są jedynymi macierzami napotykanymi w ramach obliczeń opartych na usłudze Quantum, istnieje ogólny wynik, znany jako [*widmo theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), które potwierdzają następujące kwestie: dla każdej hermitian lub macierzy jednostkowej $M $, istnieje $U jednostkowe $ to $M = U ^ \dagger D U $ dla niektórych przekątnych macierzy $D $. Ponadto, ukośne wpisy $D $ będą eigenvalues $M $.

Wiemy już, jak obliczyć eigenvalues i eigenvectors macierzy ukośnej $D $. Korzystając z tej theorem, wiemy, że jeśli $v $ jest eigenvectorem $D $ z eigenvalue $c $, tj., $Dv = CV $, wówczas $U ^ \dagger v $ będzie eigenvector $M $ z eigenvalue $c $. Dzieje się tak, ponieważ

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Wykładnicze macierze
W przypadku funkcji wykładniczej można również zdefiniować wartość [*wykładniczą macierzy*](https://en.wikipedia.org/wiki/Matrix_exponential) .  Wartość wykładnicza macierzy $A $ może być wyrażona jako

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \cdots $ $

Jest to ważne, ponieważ zmiany czasu mechanicznego w usłudze Quantum są opisane przez macierz jednostkową formularza $e ^ {iB} $ for hermitian Matrix $B $.  Z tego powodu wykonywanie wartości wykładniczych macierzy jest podstawową częścią obliczeniowej usługi Quantum i ponieważ ten Q # oferuje procedury wewnętrzne do opisywania tych operacji.
Istnieje wiele sposobów na rozliczenie matrycy wykładniczej na klasycznym komputerze i ogólnie numeryczne przybliżenie takiej wartości wykładniczej to fraught z Peril.  Zobacz [*Cleve Moler i Charles van. "Nineteen podejrzanych metody obliczeń wykładniczych macierzy". SIAM przegląd 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , aby uzyskać więcej informacji na temat wyzwań.

Najprostszym sposobem, aby zrozumieć, jak obliczyć wartość wykładniczą macierzy, za pomocą eigenvalues i eigenvectors tej macierzy.  W odniesieniu do theorem widma omówione powyżej mówi, że dla każdej hermitian lub macierzy jednostkowej $A $ istnieje macierz jednostkowa $U $ i matryca ukośna $D $, która $A = U ^ \dagger D U $.  Ze względu na właściwości unitarity, że $A ^ 2 = U ^ \dagger D ^ 2 U $ i podobne dla każdej $pej $ $A ^ p = U ^ \dagger D ^ p $.  Jeśli ta funkcja zostanie zastąpiona definicją operatora operatora wykładniczego, uzyskujemy:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2!} + \cdots \right) U = U ^ \dagger \begin{bmatrix}\exp (D_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (D_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (D_ {NN}) \end{bmatrix} U. $ $

Innymi słowy, jeśli przekształćesz na eigenbasis macierzy $A $, a następnie obliczenia wykładnicze macierzy są równoważne obliczaniu zwykłej wartości wykładniczej eigenvalues macierzy.  Ponieważ wiele operacji obliczeniowych w ramach infrastruktury Quantum obejmuje wykonywanie operacji wykładniczych matrycy, ta lewę jest niezgodna z eigenbasis macierzy, aby uprościć częstość wykonywania operatora wykładniczego i jest podstawą za wiele algorytmów Quantum, takich jak Trotter – Suzuki — metody symulacji w stylu Quantum omówione w dalszej części tego przewodnika.

Inną przydatną właściwością jest Jeśli $B $ jest zarówno jednostkowe, jak i hermitian, czyli $B = B ^{-1}= B ^ \dagger $, a następnie $B ^ 2 = \boldone $. Zastosowanie tej reguły do powyższego rozwinięcia macierzy wykładniczej i zgrupowanie elementów $ \boldone $ i $B $ terms razem może być widoczne dla każdej wartości rzeczywistej $x $

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


przechowywane. Ta lewę jest szczególnie przydatna, ponieważ pozwala na powód, aby nie zawierała wykładniczej macierzy akcji, nawet jeśli wymiar $B $ jest bardzo duży, w przypadku sytuacji, gdy $B $ jest zarówno jednostkowe, jak i hermitian.
