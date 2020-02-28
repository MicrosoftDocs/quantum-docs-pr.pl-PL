---
title: Wewnętrzne operacje i funkcje w QDK
description: Dowiedz się więcej na temat wewnętrznych operacji i funkcji w QDK, w tym funkcji klasycznych, operacji związanych z jednostką, rotacją i pomiarem.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907209"
---
# <a name="the-prelude"></a><span data-ttu-id="abcce-103">Preludium</span><span class="sxs-lookup"><span data-stu-id="abcce-103">The Prelude</span></span> #

<span data-ttu-id="abcce-104">Kompilator Q # i maszyny docelowe dołączone do zestawu Quantum Development Kit zapewniają zestaw funkcji wewnętrznych i operacji, które mogą być używane podczas pisania programów Quantum w Q #.</span><span class="sxs-lookup"><span data-stu-id="abcce-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="abcce-105">Operacje i funkcje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="abcce-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="abcce-106">Operacje wewnętrzne zdefiniowane w bibliotece standardowej w przybliżeniu należą do jednej z kilku kategorii:</span><span class="sxs-lookup"><span data-stu-id="abcce-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="abcce-107">Najważniejsze funkcje klasyczne, zbierane w przestrzeni nazw <xref:microsoft.quantum.core>.</span><span class="sxs-lookup"><span data-stu-id="abcce-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="abcce-108">Operacje reprezentujące unitaries złożone z [Clifford i $T $ bramy](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="abcce-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="abcce-109">Operacje reprezentujące rotacje różnych operatorów.</span><span class="sxs-lookup"><span data-stu-id="abcce-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="abcce-110">Operacje implementujące pomiary.</span><span class="sxs-lookup"><span data-stu-id="abcce-110">Operations implementing measurements.</span></span>

<span data-ttu-id="abcce-111">Ze względu na to, że zestaw bram Clifford + $T $ jest [uniwersalny](xref:microsoft.quantum.concepts.multiple-qubits) dla przetwarzania Quantum, te operacje wystarczą do około wdrożenia dowolnego algorytmu Quantum w ramach niewielkiego błędu.</span><span class="sxs-lookup"><span data-stu-id="abcce-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="abcce-112">Dostarczając również rotacje, program Q # umożliwia programistom współpracę w ramach jednej biblioteki bramy qubit i CNOT.</span><span class="sxs-lookup"><span data-stu-id="abcce-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="abcce-113">Ta biblioteka jest znacznie łatwiejsza, ponieważ nie wymaga od programisty bezpośredniego wyrażenia Clifford + $T $ dekompozycji i ponieważ istnieją wysoce wydajne metody kompilowania jednego qubit unitaries do Clifford i $T $ (zobacz [tutaj](xref:microsoft.quantum.more-information) , aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="abcce-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="abcce-114">Tam, gdzie to możliwe, operacje zdefiniowane w Preludium, które działają na qubits zezwala na stosowanie wariantu `Controlled`, w taki sposób, że maszyna docelowa wykona odpowiednią dekompozycję.</span><span class="sxs-lookup"><span data-stu-id="abcce-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="abcce-115">Wiele funkcji i operacji zdefiniowanych w tej części Preludium znajdują się w przestrzeni nazw @"microsoft.quantum.intrinsic", w taki sposób, że większość plików źródłowych Q # będzie miała `open Microsoft.Quantum.Intrinsic;` dyrektywy bezpośrednio po wstępnej deklaracji przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="abcce-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="abcce-116">Przestrzeń nazw <xref:microsoft.quantum.core> jest automatycznie otwierana, dzięki czemu funkcje takie jak <xref:microsoft.quantum.core.length> mogą być używane bez instrukcji `open`.</span><span class="sxs-lookup"><span data-stu-id="abcce-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="abcce-117">Typowe operacje jednostkowe pojedynczego qubit</span><span class="sxs-lookup"><span data-stu-id="abcce-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="abcce-118">Preludium definiuje także wiele typowych [operacji pojedynczych qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="abcce-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="abcce-119">Wszystkie te operacje umożliwiają zarówno `Controlled`, jak i `Adjoint` funktory.</span><span class="sxs-lookup"><span data-stu-id="abcce-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="abcce-120">Operatory Pauli</span><span class="sxs-lookup"><span data-stu-id="abcce-120">Pauli Operators</span></span> ####

<span data-ttu-id="abcce-121">Operacja <xref:microsoft.quantum.intrinsic.x> implementuje operatora Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="abcce-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="abcce-122">Jest to czasami nazywane bramą `NOT`.</span><span class="sxs-lookup"><span data-stu-id="abcce-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="abcce-123">Ma `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-124">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="abcce-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="abcce-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: obecnie używa to hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="abcce-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="abcce-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="abcce-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="abcce-127">Operacja <xref:microsoft.quantum.intrinsic.y> implementuje operatora Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="abcce-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="abcce-128">Ma `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-129">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="abcce-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="abcce-130">\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: obecnie korzysta to z.</span><span class="sxs-lookup"><span data-stu-id="abcce-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="abcce-131">i & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="abcce-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="abcce-132">Operacja <xref:microsoft.quantum.intrinsic.z> implementuje operatora Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="abcce-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="abcce-133">Ma `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-134">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="abcce-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="abcce-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: obecnie używa to hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="abcce-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="abcce-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="abcce-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="abcce-137">Zobaczymy, że te przekształcenia są zamapowane na [Bloch sfery](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (oś obrotu w każdym przypadku jest wyróżniona czerwony):</span><span class="sxs-lookup"><span data-stu-id="abcce-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Operacje Pauli zamapowane na sferę Bloch](~/media/prelude_pauliBloch.png)

<span data-ttu-id="abcce-139">Należy pamiętać, że zastosowanie tej samej bramy Pauli dwa razy do tego samego qubit powoduje anulowanie operacji (ponieważ teraz wykonano pełny obrót 2π (360 °) przez powierzchnię do kuli Bloch, a tym samym dociera do punktu początkowego.</span><span class="sxs-lookup"><span data-stu-id="abcce-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="abcce-140">Pozwala to na poniższą tożsamość:</span><span class="sxs-lookup"><span data-stu-id="abcce-140">This brings us to the following identity:</span></span>

<span data-ttu-id="abcce-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="abcce-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="abcce-142">Może to być visualised w sferze Bloch:</span><span class="sxs-lookup"><span data-stu-id="abcce-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="abcce-144">Inne pojedyncze qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="abcce-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="abcce-145">Operacja <xref:microsoft.quantum.intrinsic.h> implementuje bramę Hadamard.</span><span class="sxs-lookup"><span data-stu-id="abcce-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="abcce-146">Ta zmiana polega na tym, że Pauli $X $ i $Z $ osi docelowej qubit, takich jak $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ i $H \ket{+} = \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="abcce-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="abcce-147">Ma `(Qubit => Unit is Adj + Ctl)`podpisu i odpowiada jednemu z jednostek qubit:</span><span class="sxs-lookup"><span data-stu-id="abcce-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="abcce-148">\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: obecnie jest to e.</span><span class="sxs-lookup"><span data-stu-id="abcce-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="abcce-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="abcce-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="abcce-150">Brama Hadamard jest szczególnie ważna, ponieważ może służyć do tworzenia nadpozycji $ \ket{0}$ i $ \ket{1}$ States.</span><span class="sxs-lookup"><span data-stu-id="abcce-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="abcce-151">W reprezentacji w sferze Bloch, najłatwiej jest traktować ją jako rotacja $ \ket{\psi} $ wokół osi x przez $ \pi $ RADIANS ($ 180 ^ \circ $), po której następuje rotacja (w prawo) wokół osi y przez $ \ pi/2 $ RADIANS ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="abcce-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Operacja Hadamard zamapowana na sferę Bloch](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="abcce-153">Operacja <xref:microsoft.quantum.intrinsic.s> implementuje bramę fazy $S $.</span><span class="sxs-lookup"><span data-stu-id="abcce-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="abcce-154">To jest pierwiastek kwadratowy macierzy Pauli $Z $ operacji.</span><span class="sxs-lookup"><span data-stu-id="abcce-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="abcce-155">Oznacza to, że $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="abcce-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="abcce-156">Ma `(Qubit => Unit is Adj + Ctl)`podpisu i odpowiada jednemu z jednostek qubit:</span><span class="sxs-lookup"><span data-stu-id="abcce-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="abcce-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: obecnie używa to hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="abcce-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="abcce-158">0 & i \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="abcce-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="abcce-159">Obrotów</span><span class="sxs-lookup"><span data-stu-id="abcce-159">Rotations</span></span> ####

<span data-ttu-id="abcce-160">Oprócz powyższych operacji Pauli i Clifford, Q # Preludium oferuje różne sposoby wyrażania rotacji.</span><span class="sxs-lookup"><span data-stu-id="abcce-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="abcce-161">Zgodnie z opisem w [operacjach pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), możliwość rotacji jest niezwykle ważna dla algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="abcce-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="abcce-162">Zaczynamy od tego, że możemy wyrazić jakąkolwiek operację qubit za pomocą bram $H $ i $T $, gdzie $H $ jest operacją Hadamard i gdzie \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME</span><span class="sxs-lookup"><span data-stu-id="abcce-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="abcce-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} to jest pierwiastek kwadratowy operacji <xref:microsoft.quantum.intrinsic.s>, taki, który $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="abcce-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="abcce-164">Brama $T $ jest zaimplementowana przez operację <xref:microsoft.quantum.intrinsic.t> i ma `(Qubit => Unit is Adj + Ctl)`sygnatury, co oznacza, że jest operacją jednostkową na jednym qubit.</span><span class="sxs-lookup"><span data-stu-id="abcce-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="abcce-165">Mimo że jest to zasadniczo wystarczające do opisywania dowolnej operacji pojedynczej qubit, różne maszyny docelowe mogą być bardziej wydajnymi reprezentacjami dla rotacji o operatory Pauli, tak że Preludium zawiera różne sposoby convienently wyrażanie takich rotacji.</span><span class="sxs-lookup"><span data-stu-id="abcce-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="abcce-166">Najbardziej podstawowe są następujące operacje <xref:microsoft.quantum.intrinsic.r>, które implementują obrót wokół określonej osi Pauli, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} gdzie $ \sigma $ jest operatorem Pauli, $ \phi $ to kąt i gdzie $ \exp $ reprezentuje wartość wykładniczą macierzy.</span><span class="sxs-lookup"><span data-stu-id="abcce-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="abcce-167">Ma `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`podpisu, gdzie pierwsze dwie części danych wejściowych reprezentują klasyczne argumenty $ \sigma $ i $ \phi $, które są niezbędne do określenia operatora jednostkowego $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="abcce-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="abcce-168">Firma Microsoft może częściowo zastosować $ \sigma $ i $ \phi $, aby uzyskać operację, której typem jest moduł jednostki pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="abcce-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="abcce-169">Na przykład `R(PauliZ, PI() / 4, _)` ma `(Qubit => Unit is Adj + Ctl)`typu.</span><span class="sxs-lookup"><span data-stu-id="abcce-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="abcce-170">Operacja <xref:microsoft.quantum.intrinsic.r> dzieli kąt wejścia na 2 i mnoży ją przez-1.</span><span class="sxs-lookup"><span data-stu-id="abcce-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="abcce-171">W przypadku $Z $ rotacji oznacza to, że $ \ket{0}$ eigenstate jest obrócona o $-\phi/$2, a $ \ket{1}$ eigenstate jest obrócona o $ \phi/$2, tak aby $ \ket{1}$ eigenstate został obrócony przez $ \phi $ względem elementu $ \ket{0}$ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="abcce-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="abcce-172">W szczególności oznacza to, że `T` i `R(PauliZ, PI() / 8, _)` różnią się tylko nieistotną [fazą globalną](xref:microsoft.quantum.glossary#global-phase).</span><span class="sxs-lookup"><span data-stu-id="abcce-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="abcce-173">Z tego powodu $T $ jest czasami znany jako $ \frac{\pi}{8}$-bramę.</span><span class="sxs-lookup"><span data-stu-id="abcce-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="abcce-174">Należy również pamiętać, że obracanie wokół `PauliI` po prostu stosuje globalną fazę $ \phi/$2.</span><span class="sxs-lookup"><span data-stu-id="abcce-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="abcce-175">Chociaż takie fazy nie mają znaczenia, jak zostało to zatwierdzono w [dokumentach koncepcyjnych](xref:microsoft.quantum.concepts.qubit), są one istotne dla kontrolowanych `PauliI` obrotu.</span><span class="sxs-lookup"><span data-stu-id="abcce-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="abcce-176">W ramach algorytmów Quantum często warto wyrazić rotację jako ułamki dyadic, takie jak $ \phi = \pi k/2 ^ n $ dla niektórych $k \In \mathbb{Z} $ i $n \In \mathbb{N} $.</span><span class="sxs-lookup"><span data-stu-id="abcce-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="abcce-177">Operacja <xref:microsoft.quantum.intrinsic.rfrac> implementuje rotację wokół określonej osi Pauli przy użyciu tej Konwencji.</span><span class="sxs-lookup"><span data-stu-id="abcce-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="abcce-178">Różni się od <xref:microsoft.quantum.intrinsic.r> w tym, że kąt obrotu jest określony jako dwa dane wejściowe typu `Int`, interpretowany jako ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="abcce-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="abcce-179">W tym celu `RFrac` ma `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`sygnatury.</span><span class="sxs-lookup"><span data-stu-id="abcce-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-180">Implementuje qubit jednostki $ \exp (\pi k \sigma/2 ^ n) $, gdzie $ \sigma $ jest matrycą Pauli odpowiadającą pierwszemu argumentowi, $k $ jest drugim argumentem, a $n $ to trzeci argument.</span><span class="sxs-lookup"><span data-stu-id="abcce-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="abcce-181">`RFrac(_,k,n,_)` jest taka sama jak `R(_,-πk/2^n,_)`; Należy zauważyć, że kąt jest *wartością ujemną* części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="abcce-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="abcce-182">Operacja <xref:microsoft.quantum.intrinsic.rx> implementuje obrót wokół osi Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="abcce-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="abcce-183">Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-184">`Rx(_, _)` jest taka sama jak `R(PauliX, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="abcce-185">Operacja <xref:microsoft.quantum.intrinsic.ry> implementuje obrót wokół osi Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="abcce-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="abcce-186">Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-187">`Ry(_, _)` jest taka sama jak `R(PauliY,_ , _)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="abcce-188">Operacja <xref:microsoft.quantum.intrinsic.rz> implementuje obrót wokół osi Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="abcce-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="abcce-189">Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-190">`Rz(_, _)` jest taka sama jak `R(PauliZ, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="abcce-191">Operacja <xref:microsoft.quantum.intrinsic.r1> implementuje obrót o podaną ilość około $ \ket{1}$, $-$1 eigenstate $Z $.</span><span class="sxs-lookup"><span data-stu-id="abcce-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="abcce-192">Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-193">`R1(phi,_)` jest taka sama jak `R(PauliZ,phi,_)`, a następnie `R(PauliI,-phi,_)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="abcce-194">Operacja <xref:microsoft.quantum.intrinsic.r1frac> implementuje rotację ułamkową o podaną ilość wokół eigenstate Z = 1.</span><span class="sxs-lookup"><span data-stu-id="abcce-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="abcce-195">Ma `((Int,Int, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-196">`R1Frac(k,n,_)` jest taka sama jak `RFrac(PauliZ,-k.n+1,_)`, a następnie `RFrac(PauliI,k,n+1,_)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="abcce-197">Poniżej przedstawiono przykład operacji obrotu (wokół osi Pauli $Z $, w tym wystąpieniu) zamapowanej na sferę Bloch:</span><span class="sxs-lookup"><span data-stu-id="abcce-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Operacja obrotu zamapowana na Bloch sferę](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="abcce-199">Operacje wykonywane przez wiele qubit</span><span class="sxs-lookup"><span data-stu-id="abcce-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="abcce-200">Oprócz operacji pojedynczych qubit, Preludium także definiuje kilka operacji qubit.</span><span class="sxs-lookup"><span data-stu-id="abcce-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="abcce-201">Najpierw operacja <xref:microsoft.quantum.intrinsic.cnot> wykonuje standardowe, kontrolowane bramy`NOT`, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="abcce-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="abcce-202">\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)`, co oznacza, że $ \operatorname{CNOT} $ działa unitarily na dwóch poszczególnych qubitsach.</span><span class="sxs-lookup"><span data-stu-id="abcce-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="abcce-203">`CNOT(q1, q2)` jest taka sama jak `(Controlled X)([q1], q2)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="abcce-204">Ponieważ `Controlled` Funktor umożliwia kontrolę nad rejestrem, używamy literału Array `[q1]`, aby wskazać, że chcemy tylko jedną kontrolkę.</span><span class="sxs-lookup"><span data-stu-id="abcce-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="abcce-205">Operacja <xref:microsoft.quantum.intrinsic.ccnot> wykonuje podwójnie sterowaną bramą bez bramy, czasami również znaną jako brama Toffoli.</span><span class="sxs-lookup"><span data-stu-id="abcce-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="abcce-206">Ma `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-207">`CCNOT(q1, q2, q3)` jest taka sama jak `(Controlled X)([q1, q2], q3)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="abcce-208">Operacja <xref:microsoft.quantum.intrinsic.swap> zamienia Stany Quantum z dwóch qubitsów.</span><span class="sxs-lookup"><span data-stu-id="abcce-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="abcce-209">Oznacza to, że implementuje macierz jednostkową \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="abcce-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="abcce-210">\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="abcce-211">`SWAP(q1,q2)` jest równoważne `CNOT(q1, q2)`, a następnie `CNOT(q2, q1)` a następnie `CNOT(q1, q2)`.</span><span class="sxs-lookup"><span data-stu-id="abcce-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="abcce-212">Brama wymiany *nie* jest taka sama jak zmiana układu elementów zmiennej typu `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="abcce-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="abcce-213">Zastosowanie `SWAP(q1, q2)` powoduje zmianę stanu qubits, do którego odwołuje się `q1` i `q2`, natomiast `let swappedRegister = [q2, q1];` ma wpływ tylko na te qubits.</span><span class="sxs-lookup"><span data-stu-id="abcce-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="abcce-214">Ponadto `(Controlled SWAP)([q0], (q1, q2))` pozwala na Kondycjonowanie `SWAP` na stanie qubit trzeciego, którego nie można reprezentować przez ponowne rozmieszczenie elementów.</span><span class="sxs-lookup"><span data-stu-id="abcce-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="abcce-215">Brama przełączenia kontrolowanego, znana także jako brama Fredkin, jest wystarczająco wydajna, aby obejmowała wszystkie klasyczne obliczenia.</span><span class="sxs-lookup"><span data-stu-id="abcce-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="abcce-216">Na koniec Preludium zawiera dwie operacje do reprezentowania wykładniczych operatorów wieloqubitowych Pauli.</span><span class="sxs-lookup"><span data-stu-id="abcce-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="abcce-217">Operacja <xref:microsoft.quantum.intrinsic.exp> wykonuje rotację na podstawie iloczynu Pauli macierzy. reprezentowane przez wieloqubitne \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} WHERE $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ jest sekwencją operatorów pojedyncze-qubit Pauli i gdzie $ \phi $ jest kątem.</span><span class="sxs-lookup"><span data-stu-id="abcce-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="abcce-218">Obrót `Exp` reprezentuje $ \vec{\sigma} $ jako tablicę elementów `Pauli`, tak że ma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`sygnatur.</span><span class="sxs-lookup"><span data-stu-id="abcce-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="abcce-219">Operacja <xref:microsoft.quantum.intrinsic.expfrac> wykonuje ten sam obrót przy użyciu notacji dyadic ułamków opisanej powyżej.</span><span class="sxs-lookup"><span data-stu-id="abcce-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="abcce-220">Ma `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="abcce-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="abcce-221">Wartość wykładnicza iloczynu dwuczęściowego w operatorach Pauli nie jest taka sama jak iloczynów dwuczęściowych operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="abcce-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="abcce-222">Oznacza to, że $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="abcce-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="abcce-223">Miary</span><span class="sxs-lookup"><span data-stu-id="abcce-223">Measurements</span></span> ###

<span data-ttu-id="abcce-224">Podczas mierzenia, wartość + 1 eigenvaluea operatora jest mierzona w wyniku `Zero` i-1 eigenvalue do wyniku `One`.</span><span class="sxs-lookup"><span data-stu-id="abcce-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="abcce-225">Chociaż ta konwencja może wydawać się nieparzysta, ma dwie zalety.</span><span class="sxs-lookup"><span data-stu-id="abcce-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="abcce-226">Po pierwsze obserwowanie wyniku $ \ket{0}$ jest reprezentowane przez `Result` wartość `Zero`, podczas gdy przestrzeganie $ \ket{1}$ odpowiada `One`.</span><span class="sxs-lookup"><span data-stu-id="abcce-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="abcce-227">Następnie możemy napisać, że eigenvalue $ \lambda $ odpowiadający wynikowi $r $ to $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="abcce-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="abcce-228">Operacje pomiarów obsługują nie `Adjoint` ani `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="abcce-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="abcce-229">Operacja <xref:microsoft.quantum.intrinsic.measure> wykonuje wspólne pomiary co najmniej jednego qubits w określonym produkcie operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="abcce-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="abcce-230">Jeśli macierz Pauli i tablica qubit mają różne długości, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="abcce-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="abcce-231">`Measure` ma `((Pauli[], Qubit[]) => Result)`sygnatury.</span><span class="sxs-lookup"><span data-stu-id="abcce-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="abcce-232">Należy zauważyć, że wspólne pomiary nie są takie same jak pomiary każdego qubit indywidualnie.</span><span class="sxs-lookup"><span data-stu-id="abcce-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="abcce-233">Rozważmy na przykład stan $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span><span class="sxs-lookup"><span data-stu-id="abcce-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="abcce-234">Pomiary $Z _0 $ i $Z _1 $ osobno, uzyskujemy wyniki $r _0 = $1 i $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="abcce-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="abcce-235">Pomiar $Z _0 Z_1 $, jednak pobieramy pojedynczy wynik $r _ {\textrm{joint}}d = $0, co oznacza, że para $ \ket{11}$ jest dodatnia.</span><span class="sxs-lookup"><span data-stu-id="abcce-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="abcce-236">Umieść inaczej: $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="abcce-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="abcce-237">Ze względu na to, że pouczymy się *tylko* o parzystości z tego pomiaru, wszystkie informacje o Quantum, które są reprezentowane w rozłożeniu między 2 2 qubit Stanów pozytywnej parzystości, $ \ket{00}$ i $ \ket{11}$, są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="abcce-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="abcce-238">Ta właściwość będzie istotna w przyszłości, ponieważ omawiamy korekcję błędów.</span><span class="sxs-lookup"><span data-stu-id="abcce-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="abcce-239">Dla wygody Preludium również obejmuje dwie inne operacje do mierzenia qubits.</span><span class="sxs-lookup"><span data-stu-id="abcce-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="abcce-240">Najpierw ponieważ wykonywanie pomiarów qubit jest dość popularne, Preludium definiuje skrót dla tego przypadku.</span><span class="sxs-lookup"><span data-stu-id="abcce-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="abcce-241">Operacja <xref:microsoft.quantum.intrinsic.m> mierzy operator Pauli $Z $ na jednym qubit i ma `(Qubit => Result)`sygnatur.</span><span class="sxs-lookup"><span data-stu-id="abcce-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="abcce-242">`M(q)` jest równoznaczna z `Measure([PauliZ], [q])`.</span><span class="sxs-lookup"><span data-stu-id="abcce-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="abcce-243"><xref:microsoft.quantum.measurement.multim> mierzy operator Pauli $Z $ *osobno* dla każdej tablicy qubits, zwracając *tablicę* wartości `Result` uzyskanych dla każdego qubit.</span><span class="sxs-lookup"><span data-stu-id="abcce-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="abcce-244">W niektórych przypadkach może to być zoptymalizowane.</span><span class="sxs-lookup"><span data-stu-id="abcce-244">In some cases this can be optimized.</span></span> <span data-ttu-id="abcce-245">Ma sygnaturę (`Qubit[] => Result[])`.</span><span class="sxs-lookup"><span data-stu-id="abcce-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="abcce-246">`MultiM(qs)` jest równoważne:</span><span class="sxs-lookup"><span data-stu-id="abcce-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="abcce-247">Funkcje i operacje rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="abcce-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="abcce-248">Ponadto Preludium definiuje bogaty zestaw funkcji konwersji matematycznych i typów na poziomie platformy .NET do użycia w kodzie Q #.</span><span class="sxs-lookup"><span data-stu-id="abcce-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="abcce-249">Na przykład przestrzeń nazw <xref:microsoft.quantum.extensions.math> definiuje użyteczne operacje, takie jak <xref:microsoft.quantum.extensions.math.sin> i <xref:microsoft.quantum.extensions.math.log>.</span><span class="sxs-lookup"><span data-stu-id="abcce-249">For instance, the <xref:microsoft.quantum.extensions.math> namespace defines useful operations such as <xref:microsoft.quantum.extensions.math.sin> and <xref:microsoft.quantum.extensions.math.log>.</span></span>
<span data-ttu-id="abcce-250">Implementacja udostępniona przez zestaw Quantum Development Kit używa klasycznej biblioteki klas .NET, co może wiązać się z dodatkową komunikacją między programami Quantum i ich klasycznymi sterownikami.</span><span class="sxs-lookup"><span data-stu-id="abcce-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="abcce-251">Chociaż nie ma to problemu dla lokalnego symulatora, może to być problem z wydajnością w przypadku korzystania z zdalnego symulatora lub rzeczywistego sprzętu jako maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="abcce-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="abcce-252">Ten sam komputer docelowy może wyeliminować ten wpływ na wydajność, zastępując te operacje niektórymi wersjami, które są bardziej wydajne dla danego systemu.</span><span class="sxs-lookup"><span data-stu-id="abcce-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="abcce-253">Dodatku</span><span class="sxs-lookup"><span data-stu-id="abcce-253">Math</span></span> ###

<span data-ttu-id="abcce-254">Przestrzeń nazw <xref:microsoft.quantum.extensions.math> zawiera wiele przydatnych funkcji z [klasy`System.Math`](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)biblioteki klas podstawowych platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="abcce-254">The <xref:microsoft.quantum.extensions.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="abcce-255">Te funkcje mogą być używane w taki sam sposób jak w przypadku innych funkcji Q #:</span><span class="sxs-lookup"><span data-stu-id="abcce-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="abcce-256">Gdzie metoda statyczna platformy .NET została przeciążona na podstawie typu argumentów, odpowiednia funkcja Q # ma adnotację z sufiksem wskazującym typ danych wejściowych:</span><span class="sxs-lookup"><span data-stu-id="abcce-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="abcce-257">Operacje bitowe</span><span class="sxs-lookup"><span data-stu-id="abcce-257">Bitwise Operations</span></span> ###

<span data-ttu-id="abcce-258">Na koniec przestrzeń nazw <xref:microsoft.quantum.extensions.bitwise> zawiera kilka przydatnych funkcji służących do manipulowania liczbami całkowitymi za pomocą operatorów bitowych.</span><span class="sxs-lookup"><span data-stu-id="abcce-258">Finally, the <xref:microsoft.quantum.extensions.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="abcce-259">Na przykład, <xref:microsoft.quantum.extensions.bitwise.parity> zwraca bitową parzystość liczby całkowitej jako inną liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="abcce-259">For instance, <xref:microsoft.quantum.extensions.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
