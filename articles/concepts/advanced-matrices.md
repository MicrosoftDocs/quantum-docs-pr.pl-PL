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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630150"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="f53e1-103">Zaawansowane koncepcje macierzy</span><span class="sxs-lookup"><span data-stu-id="f53e1-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="f53e1-104">Teraz rozszerzamy manipulowanie macierzami na [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) i [*wykładnicze*](https://en.wikipedia.org/wiki/Matrix_exponential) , które tworzą podstawowy zestaw narzędzi potrzebnych do opisywania i implementowania algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="f53e1-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="f53e1-105">Eigenvalues i Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="f53e1-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="f53e1-106">Niech $M $ być tablicą kwadratową i $v $ być wektorem, który nie jest wektorem "All Zeros" (tj. wektor ze wszystkimi pozycjami równymi $0 $ ).</span><span class="sxs-lookup"><span data-stu-id="f53e1-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="f53e1-107">Załóżmy, że $v $ jest [*eigenvectorem*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $M, $ Jeśli $MV = CV $ dla niektórych $c liczby $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="f53e1-108">Załóżmy, $c $ jest [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpowiadający $v eigenvector $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="f53e1-109">Ogólnie rzecz biorąc, macierz $M $ może przekształcić wektor w inne wektory, ale eigenvector jest specjalny, ponieważ pozostanie niezmieniony, z wyjątkiem tego, że jest mnożony przez liczbę.</span><span class="sxs-lookup"><span data-stu-id="f53e1-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="f53e1-110">Należy pamiętać, że jeśli $v $ jest eigenvector z eigenvalue $c $ , wówczas $AV $ jest również eigenvector (dla dowolnej niezerowej $a $ ) z tym samym eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="f53e1-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="f53e1-111">Na przykład w przypadku macierzy tożsamości każda $v wektora $ jest eigenvector z eigenvalue $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="f53e1-112">Innym przykładem jest rozważenie $D [*macierzy ukośnej*](https://en.wikipedia.org/wiki/Diagonal_matrix) , $ która ma tylko niezerowe wpisy na przekątnej:</span><span class="sxs-lookup"><span data-stu-id="f53e1-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="f53e1-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f53e1-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="f53e1-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f53e1-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f53e1-115">Wektory</span><span class="sxs-lookup"><span data-stu-id="f53e1-115">The vectors</span></span>

<span data-ttu-id="f53e1-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ \end{ bmatrix } , \begin{ bmatrix } 0, \\ \\ \\ \\ 0 \end { bmatrix } i \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f53e1-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="f53e1-117">są eigenvectors tej macierzy z eigenvalues $d _1 $ , $d _2 $ i $d _3 $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="f53e1-118">Jeśli $d _1 $ , $d _2 $ i $d _3 $ to odrębne liczby, wówczas te wektory (i ich wielokrotność) są jedynymi eigenvectorsami $D macierzy $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="f53e1-119">Ogólnie rzecz biorąc, w przypadku matrycy ukośnej można łatwo odczytywać eigenvalues i eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="f53e1-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="f53e1-120">Eigenvalues są wszystkie liczby wyświetlane na przekątnej, a ich odpowiednie eigenvectors to wektory jednostek z jednym wpisem równym $1, $ a pozostałe wpisy są równe $0 $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="f53e1-121">Zwróć uwagę, że w powyższym przykładzie eigenvectors $D $ stanowią podstawę dla $ wektorów $3.</span><span class="sxs-lookup"><span data-stu-id="f53e1-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="f53e1-122">Podstawą jest zestaw wektorów, tak że każdy wektor może być zapisany jako liniowa kombinacja.</span><span class="sxs-lookup"><span data-stu-id="f53e1-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="f53e1-123">Bardziej jawnie, $v _1 $ , $v _2 $ i $v _3, a $ $v wektorów $ można napisać jako $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ dla niektórych liczb $a _1 $ , $a _2 $ i $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="f53e1-124">Należy przypomnieć, że macierz hermitian (nazywana również własnym) jest złożoną jednostkową tablicą równą jej własnej złożonej sprzężonej, podczas gdy macierz jednostkowa to złożona macierz kwadratowa, której odwrotność jest równa jego złożonej sprzężonej.</span><span class="sxs-lookup"><span data-stu-id="f53e1-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="f53e1-125">W przypadku hermitian i macierzy jednostkowych, które zasadniczo są jedyne macierzy spotykanych w ramach obliczeń opartych na usłudze Quantum, istnieje ogólny wynik, znany jako [*widmo theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), które potwierdzają następujące kwestie: dla każdej Hermitianowej lub $mej macierzy $ , istnieje $U, $ która $M = U ^ \dagger D u $ dla niektórych przekątnych macierzy $D $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="f53e1-126">Ponadto, ukośne wpisy $D $ będą eigenvalues $M $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="f53e1-127">Wiemy już, jak obliczyć eigenvalues i eigenvectors macierzy ukośnej $D $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="f53e1-128">Korzystając z tej theorem, wiemy, że jeśli $v $ jest eigenvector $D $ z eigenvalue $c $ , tj., $DV = CV $ , a następnie $U ^ \dagger v $ będzie eigenvector $M $ z eigenvalue $c $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="f53e1-129">Dzieje się tak, ponieważ</span><span class="sxs-lookup"><span data-stu-id="f53e1-129">This is because</span></span>

<span data-ttu-id="f53e1-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="f53e1-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="f53e1-131">Wykładnicze macierze</span><span class="sxs-lookup"><span data-stu-id="f53e1-131">Matrix Exponentials</span></span>
<span data-ttu-id="f53e1-132">W przypadku funkcji wykładniczej można również zdefiniować wartość [*wykładniczą macierzy*](https://en.wikipedia.org/wiki/Matrix_exponential) .</span><span class="sxs-lookup"><span data-stu-id="f53e1-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="f53e1-133">Wartość wykładnicza macierzy $A macierzy $ może być wyrażona jako</span><span class="sxs-lookup"><span data-stu-id="f53e1-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="f53e1-134">$ $ e ^ A = \boldone + A + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="f53e1-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="f53e1-135">Jest to ważne, ponieważ zmiana czasu mechanicznego Quantum jest opisana przez macierz jednostkową formularza $e ^ {iB } $ for hermitian matrix $B $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="f53e1-136">Z tego powodu wykonywanie wartości wykładniczych macierzy jest podstawową częścią obliczeniowej usługi Quantum i ponieważ ten Q # oferuje procedury wewnętrzne do opisywania tych operacji.</span><span class="sxs-lookup"><span data-stu-id="f53e1-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="f53e1-137">Istnieje wiele sposobów na rozliczenie matrycy wykładniczej na klasycznym komputerze i ogólnie numeryczne przybliżenie takiej wartości wykładniczej to fraught z Peril.</span><span class="sxs-lookup"><span data-stu-id="f53e1-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="f53e1-138">Zobacz [*Cleve Moler i Charles van. "Nineteen podejrzanych metody obliczeń wykładniczych macierzy". SIAM przegląd 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , aby uzyskać więcej informacji na temat wyzwań.</span><span class="sxs-lookup"><span data-stu-id="f53e1-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="f53e1-139">Najprostszym sposobem, aby zrozumieć, jak obliczyć wartość wykładniczą macierzy, za pomocą eigenvalues i eigenvectors tej macierzy.</span><span class="sxs-lookup"><span data-stu-id="f53e1-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="f53e1-140">W odniesieniu do theorem widma opisanego powyżej mówi, że dla każdej hermitian lub macierzy jednostkowej $A $ istnieje macierz jednostkowa $U $ i matryca ukośna $D $ taka $A = U ^ \dagger D u $ .  Ze względu na właściwości unitarity, że $A ^ 2 = U ^ \dagger D ^ 2 U $ i podobne dla dowolnego $PA, $ $A ^ p = U ^ \dagger D ^ p U $ .  Jeśli ta funkcja zostanie zastąpiona definicją operatora operatora wykładniczego, uzyskujemy:</span><span class="sxs-lookup"><span data-stu-id="f53e1-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="f53e1-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="f53e1-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="f53e1-142">Innymi słowy, jeśli przekształcisz się na eigenbasis $A macierzy, $ a następnie obliczenia wykładnicze macierzy są równoważne do obliczania zwykłej wykładniczej eigenvalues macierzy.</span><span class="sxs-lookup"><span data-stu-id="f53e1-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="f53e1-143">Ponieważ wiele operacji obliczeniowych opartych na infrastrukturze opartej na protokole Quantum obejmuje wykonywanie wartości wykładniczych macierzy, to ta część transformacji w eigenbasis macierzy, która upraszcza wykonywanie operatora wykładniczego, i jest podstawą za wiele algorytmów Quantum, takich jak Trotter – Suzuki-style metody symulacji w dalszej części tego przewodnika.</span><span class="sxs-lookup"><span data-stu-id="f53e1-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="f53e1-144">Inną przydatną właściwością jest to, że $B $ jest zarówno jednostkowa, jak i hermitian, czyli $B = b ^ {-1 } = B ^ \dagger, $ a następnie $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="f53e1-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="f53e1-145">Zastosowanie tej reguły do powyższego rozwinięcia macierzy wykładniczej i przez zgrupowanie wartości $ \boldone $ oraz $Bych $ warunków może być widoczne dla każdej wartości rzeczywistej $x $ tożsamości</span><span class="sxs-lookup"><span data-stu-id="f53e1-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="f53e1-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="f53e1-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="f53e1-147">przechowywane.</span><span class="sxs-lookup"><span data-stu-id="f53e1-147">holds.</span></span> <span data-ttu-id="f53e1-148">Ta lewę jest szczególnie przydatna, ponieważ pozwala na to przyczynę o wartościach wykładniczych macierzy akcji, nawet jeśli wymiar $B $ jest duży, w przypadku sytuacji, gdy $B $ jest zarówno jednostkowe, jak i hermitian.</span><span class="sxs-lookup"><span data-stu-id="f53e1-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
