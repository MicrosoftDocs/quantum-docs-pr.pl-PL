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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630203"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="fd486-103">Wektory i macierze</span><span class="sxs-lookup"><span data-stu-id="fd486-103">Vectors and Matrices</span></span>

<span data-ttu-id="fd486-104">Znajomość wektorów i macierzy jest niezbędna do zrozumienia przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd486-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="fd486-105">Udostępniamy krótkie wprowadzenie poniżej, a zainteresowani czytelnicy są zalecani do odczytania standardowego odwołania do algebry liniowego *, takiego jak Strang, G. (1993). Wprowadzenie do liniowej algebry (obj. 3). Wellesley, MA: Wellesley-Cambridge naciśnij* lub odwołanie online, takie jak [liniowe algebry](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="fd486-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="fd486-106">Wektor kolumny (lub po prostu [*wektor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ wymiaru (lub rozmiaru) $n $ jest kolekcją $n $ liczb zespolonych $ (v_1, v_2, \ldots, v_n) $ ułożone jako kolumna:</span><span class="sxs-lookup"><span data-stu-id="fd486-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="fd486-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-108">v_1\\\\</span></span>
<span data-ttu-id="fd486-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-109">v_2\\\\</span></span>
<span data-ttu-id="fd486-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-110">\vdots\\\\</span></span>
<span data-ttu-id="fd486-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="fd486-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="fd486-112">Norma $v wektora $ jest definiowana jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $.</span><span class="sxs-lookup"><span data-stu-id="fd486-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="fd486-113">Wektor jest określany jako wartość normy jednostkowej (lub alternatywnie jest nazywany [*wektorem jednostki*](https://en.wikipedia.org/wiki/Unit_vector)), jeśli jego normą jest $1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="fd486-114">[*Sąsiadująca $v wektora*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ jest oznaczona $v ^ \dagger $ i jest zdefiniowana jako wektor wiersza, gdzie $ \* $ oznacza złożony sprzężony,</span><span class="sxs-lookup"><span data-stu-id="fd486-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="fd486-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="fd486-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="fd486-116">Najbardziej typowym sposobem mnożenia dwóch wektorów jest użycie [*wewnętrznego produktu*](https://en.wikipedia.org/wiki/Inner_product_space), znanego również jako iloczyn kropki.</span><span class="sxs-lookup"><span data-stu-id="fd486-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="fd486-117">Wewnętrzny produkt daje rzutowanie jednego wektora na inny i jest niecenny w opisie, jak wyznaczać jeden wektor jako sumę innych łatwiejszych wektorów.</span><span class="sxs-lookup"><span data-stu-id="fd486-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="fd486-118">Wewnętrzny produkt między $u $ i $v $ , oznaczany $ \left \langle u, v \right \rangle $ jest zdefiniowany jako</span><span class="sxs-lookup"><span data-stu-id="fd486-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="fd486-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="fd486-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="fd486-120">Ten zapis umożliwia także zapisanie normy $v wektora $ jako $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="fd486-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="fd486-121">Możemy pomnożyć wektor z liczbą $c $ , aby utworzyć nowy wektor, którego wpisy są mnożone przez $c $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="fd486-122">Możemy również dodać dwa wektory $u $ i $v, $ Aby utworzyć nowy wektor, którego wpisy są sumą wpisów $u $ i $v $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="fd486-123">Poniżej przedstawiono następujące operacje:</span><span class="sxs-lookup"><span data-stu-id="fd486-123">These operations are depicted below:</span></span>

<span data-ttu-id="fd486-124">$ $ \mathrm{If } ~ = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-125">u_1\\\\</span></span>
<span data-ttu-id="fd486-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-126">u_2\\\\</span></span>
<span data-ttu-id="fd486-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-127">\vdots\\\\</span></span>
<span data-ttu-id="fd486-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-129">v_1\\\\</span></span>
    <span data-ttu-id="fd486-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-130">v_2\\\\</span></span>
    <span data-ttu-id="fd486-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-131">\vdots\\\\</span></span>
    <span data-ttu-id="fd486-132">v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="fd486-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="fd486-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-135">\vdots\\\\</span></span>
<span data-ttu-id="fd486-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd486-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="fd486-137">[*Macierz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) rozmiaru $m \times n $ to zbiór $MN $ liczby zespolone uporządkowane w $m $ wiersze i $n $ kolumny, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="fd486-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="fd486-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="fd486-139">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="fd486-140">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="fd486-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="fd486-141">Należy zauważyć, że wektor wymiaru $n $ jest po prostu macierzy rozmiaru $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="fd486-142">Podobnie jak w przypadku wektorów możemy pomnożyć macierz z liczbą $c, $ Aby uzyskać nową macierz, w której każdy wpis jest mnożony przez $c $ , i możemy dodać dwie macierze o tym samym rozmiarze, aby utworzyć nową macierz, której wpisy są sumą odpowiednich wpisów dwóch macierzy.</span><span class="sxs-lookup"><span data-stu-id="fd486-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="fd486-143">Iloczyny i wielokrotność macierzy</span><span class="sxs-lookup"><span data-stu-id="fd486-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="fd486-144">Możemy również pomnożyć dwie macierze $M $ wymiar $m \times n $ i $N $ wymiar $n \times p $ w celu uzyskania nowej macierzy $P $ wymiarów $m \times p $ w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fd486-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="fd486-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-145">\begin{align}</span></span>
<span data-ttu-id="fd486-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-147">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="fd486-148">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="fd486-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="fd486-149">punktówbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-149">\end{bmatrix}</span></span>
<span data-ttu-id="fd486-150">zacznąbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-150">\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ { } \\ \\ data\ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="fd486-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {np}</span><span class="sxs-lookup"><span data-stu-id="fd486-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="fd486-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-154">P_ {11 } ~ ~ p_ {12 } ~ ~ \cdots ~ ~ p_ {1p } \\ \\ p_ {21 } ~ ~ p_ {22 } ~ ~ \cdots ~ ~ p_ { } \\ \\ data\ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="fd486-155">P_ {M1 } ~ ~ p_ {m2 } ~ ~ \cdots ~ ~ p_ {MP}</span><span class="sxs-lookup"><span data-stu-id="fd486-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="fd486-156">punktówbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-156">\end{bmatrix}</span></span>
<span data-ttu-id="fd486-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-157">\end{align}</span></span>

<span data-ttu-id="fd486-158">miejsce, w którym wpisy $P $ są $P _ {IK } = \ sum_j m_ {ij} N_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="fd486-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="fd486-159">Na przykład wpis $P _ {11 } $ jest wewnętrznym produktem pierwszego wiersza $M $ z pierwszą kolumną $N $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="fd486-160">Należy zauważyć, że ponieważ wektor jest po prostu szczególnym przypadkiem macierzy, ta definicja rozciąga się na liczebność wektora.</span><span class="sxs-lookup"><span data-stu-id="fd486-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="fd486-161">Wszystkie używane macierze będą macierzami kwadratowymi, gdzie liczba wierszy i kolumn jest równa lub wektorów, które odnoszą się tylko do $1 $ kolumn.</span><span class="sxs-lookup"><span data-stu-id="fd486-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="fd486-162">Jedna specjalna macierz kwadratowa to [*macierz tożsamości*](https://en.wikipedia.org/wiki/Identity_matrix), oznaczona jako $ \boldone $ , która ma wszystkie elementy ukośne równe $1 $ i pozostałe elementy równe $0 $ :</span><span class="sxs-lookup"><span data-stu-id="fd486-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="fd486-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="fd486-164">1 ~ ~ 0 ~ ~ \cdots ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="fd486-165">0 ~ ~ ~ ~ \cdots ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="fd486-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="fd486-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="fd486-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="fd486-168">W przypadku $A macierzy kwadratowej $ Załóżmy, że macierz $B $ jest jej [*odwracania*](https://en.wikipedia.org/wiki/Invertible_matrix) , jeśli $AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="fd486-169">Odwrotność macierzy nie powinna istnieć, ale gdy istnieje, jest unikatowa, a My wskazujemy ją $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="fd486-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="fd486-170">W przypadku każdej $M macierzy $ , sąsiadująca lub sprzężona transtransponowana $M $ to macierz $N $ taka, która $N _ {IJ } = m_ {ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="fd486-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="fd486-171">Sąsiadujące $M $ jest zwykle oznaczone $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="fd486-172">Załóżmy, że macierz $U $ jest [*jednostką*](https://en.wikipedia.org/wiki/Unitary_matrix) , jeśli $uu ^ \dagger = U ^ \dagger U = \boldone $ lub równoważne, $U ^ {-1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="fd486-173">Być może najważniejszym właściwością macierzy jednostkowych jest zachowanie normy wektora.</span><span class="sxs-lookup"><span data-stu-id="fd486-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="fd486-174">Dzieje się tak, ponieważ</span><span class="sxs-lookup"><span data-stu-id="fd486-174">This happens because</span></span> 

<span data-ttu-id="fd486-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="fd486-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="fd486-176">$M macierzy $ jest określana jako [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , jeśli $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="fd486-177">Na koniec, [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (lub Kronecker produkt) dwóch macierzy $M $ rozmiaru $m \times n $ i $N $ rozmiaru $p \times q $ to większa macierz $P = M \otimes n $ rozmiaru $MP \times NQ $ i jest uzyskiwana z $M $ i $N $ w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fd486-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="fd486-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-178">\begin{align}</span></span>
    <span data-ttu-id="fd486-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-180">M_ {11 } ~ ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="fd486-181">M_ {M1 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="fd486-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="fd486-182">punktówbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-182">\end{bmatrix}</span></span>
    <span data-ttu-id="fd486-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-184">N_ {11 } ~ ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="fd486-185">N_ {P1 } ~ ~ ~ \cdots ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="fd486-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="fd486-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } N_ {11 } ~ } \\ \\ \\\\ } } bmatrix } \\ \\ ~ \cdots ~ ~ N_ {1Q \ddots N_\\\\</span><span class="sxs-lookup"><span data-stu-id="fd486-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="fd486-188">M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {MN } \begin{ bmatrix } N_ {11 } ~ } \\ \\ \\\\ } } ~ \cdots ~ ~ N_ {1Q \ddots N_bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd486-189">\end{bmatrix}.</span></span>
<span data-ttu-id="fd486-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-190">\end{align}</span></span>

<span data-ttu-id="fd486-191">Jest to lepsza Prezentacja z kilkoma przykładami:</span><span class="sxs-lookup"><span data-stu-id="fd486-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="fd486-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="fd486-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="fd486-196">punktówbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-196">\end{bmatrix}</span></span>
    <span data-ttu-id="fd486-197">= \begin{ bmatrix } a c a a \\ \\ \\ \\ e \\ \\ b c b \\ \\ d \\ \\ \end a to {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="fd486-198">oraz</span><span class="sxs-lookup"><span data-stu-id="fd486-198">and</span></span>

<span data-ttu-id="fd486-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="fd486-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="fd486-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-204">\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="fd486-212">punktówbmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-212">\end{bmatrix}</span></span>
    <span data-ttu-id="fd486-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd486-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="fd486-214">AE \ AF \ to \ \\ \\ DBAG \ Ah \ BG \ BH \\ \\ ce \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd486-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="fd486-215">Końcową, użyteczną Konwencją notacji otaczającą produkty dla każdego z nich, jest to, że dla dowolnego $v wektorów $ lub $M macierzy $ $v ^ {\otimes n } $ lub $M ^ {\otimes n } $ jest krótką ręką w przypadku ciągłego naliczania na $n $ .</span><span class="sxs-lookup"><span data-stu-id="fd486-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="fd486-216">Przykład:</span><span class="sxs-lookup"><span data-stu-id="fd486-216">For example:</span></span>

<span data-ttu-id="fd486-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-217">\begin{align}</span></span>
<span data-ttu-id="fd486-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 0 &0 \\ \\&1 \\ \\ \\\\ \end bmatrix }&0 0 &1&0&0</span><span class="sxs-lookup"><span data-stu-id="fd486-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="fd486-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd486-219">\end{align}</span></span>
