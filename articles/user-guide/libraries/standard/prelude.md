---
title: Wewnętrzne operacje i funkcje w QDK
description: Dowiedz się więcej na temat wewnętrznych operacji i funkcji w QDK, w tym funkcji klasycznych, operacji związanych z jednostką, rotacją i pomiarem.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4eb10e82a64381c503703be440be90e60f3a8622
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863725"
---
# <a name="the-prelude"></a><span data-ttu-id="4ce8c-103">Preludium</span><span class="sxs-lookup"><span data-stu-id="4ce8c-103">The Prelude</span></span> #

<span data-ttu-id="4ce8c-104">Q#Kompilator i maszyny docelowe dołączone do zestawu Quantum Development Kit zapewniają zestaw funkcji wewnętrznych i operacji, które mogą być używane podczas pisania programów Quantum w systemie Q# .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="4ce8c-105">Operacje i funkcje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="4ce8c-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="4ce8c-106">Operacje wewnętrzne zdefiniowane w bibliotece standardowej w przybliżeniu należą do jednej z kilku kategorii:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="4ce8c-107">Najważniejsze funkcje klasyczne, zebrane w <xref:microsoft.quantum.core> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="4ce8c-108">Operacje reprezentujące unitaries złożone z [Clifford i $T $ bramy](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="4ce8c-109">Operacje reprezentujące rotacje różnych operatorów.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="4ce8c-110">Operacje implementujące pomiary.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-110">Operations implementing measurements.</span></span>

<span data-ttu-id="4ce8c-111">Ze względu na to, że zestaw bram Clifford + $T $ jest [uniwersalny](xref:microsoft.quantum.concepts.multiple-qubits) dla przetwarzania Quantum, te operacje wystarczą do około wdrożenia dowolnego algorytmu Quantum w ramach niewielkiego błędu.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="4ce8c-112">Dostarczając również rotacje, Q# pozwala programistie na działanie w ramach jednej biblioteki bramy qubit i CNOT.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="4ce8c-113">Ta biblioteka jest znacznie łatwiejsza, ponieważ nie wymaga od programisty bezpośredniego wyrażenia Clifford + $T $ dekompozycji i ponieważ istnieją wysoce wydajne metody kompilowania jednego qubit unitaries do Clifford i $T $ (zobacz [tutaj](xref:microsoft.quantum.more-information) , aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="4ce8c-114">Tam, gdzie to możliwe, operacje zdefiniowane w Preludium, które działają na qubits zezwala na stosowanie `Controlled` wariantu, w taki sposób, że maszyna docelowa wykona odpowiednią dekompozycję.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="4ce8c-115">Wiele funkcji i operacji zdefiniowanych w tej części Preludium znajdują się w @"microsoft.quantum.intrinsic" przestrzeni nazw, w taki sposób, że większość Q# plików źródłowych będzie miała `open Microsoft.Quantum.Intrinsic;` dyrektywę natychmiast po wstępnej deklaracji przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="4ce8c-116"><xref:microsoft.quantum.core>Przestrzeń nazw jest automatycznie otwierana, dzięki czemu funkcje takie jak <xref:microsoft.quantum.core.length> mogą być używane bez `open` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="4ce8c-117">Typowe operacje jednostkowe pojedynczego qubit</span><span class="sxs-lookup"><span data-stu-id="4ce8c-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="4ce8c-118">Preludium definiuje także wiele typowych [operacji pojedynczych qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="4ce8c-119">Wszystkie te operacje umożliwiają zarówno `Controlled` funktory, jak i `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="4ce8c-120">Operatory Pauli</span><span class="sxs-lookup"><span data-stu-id="4ce8c-120">Pauli Operators</span></span> ####

<span data-ttu-id="4ce8c-121"><xref:microsoft.quantum.intrinsic.x>Operacja implementuje operator Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="4ce8c-122">Jest to czasami nazywane `NOT` bramą.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="4ce8c-123">Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-124">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4ce8c-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: obecnie używa ona hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4ce8c-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4ce8c-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4ce8c-127"><xref:microsoft.quantum.intrinsic.y>Operacja implementuje operator Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="4ce8c-128">Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-129">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4ce8c-130">\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: obecnie korzysta to z hakerów quadwhack.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4ce8c-131">i & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4ce8c-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4ce8c-132"><xref:microsoft.quantum.intrinsic.z>Operacja implementuje operator Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="4ce8c-133">Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-134">Odnosi się do jednostki pojedynczej qubit:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4ce8c-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie używa to hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4ce8c-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4ce8c-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4ce8c-137">Zobaczymy, że te przekształcenia są zamapowane na [Bloch sfery](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (oś obrotu w każdym przypadku jest wyróżniona czerwony):</span><span class="sxs-lookup"><span data-stu-id="4ce8c-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Operacje Pauli zamapowane na sferę Bloch](~/media/prelude_pauliBloch.png)

<span data-ttu-id="4ce8c-139">Należy pamiętać, że zastosowanie tej samej bramy Pauli dwa razy do tego samego qubit powoduje anulowanie operacji (ponieważ teraz wykonano pełny obrót 2π (360 °) przez powierzchnię do kuli Bloch, a tym samym dociera do punktu początkowego.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="4ce8c-140">Pozwala to na poniższą tożsamość:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-140">This brings us to the following identity:</span></span>

<span data-ttu-id="4ce8c-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="4ce8c-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="4ce8c-142">Może to być visualised w sferze Bloch:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="4ce8c-144">Inne pojedyncze qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="4ce8c-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="4ce8c-145"><xref:microsoft.quantum.intrinsic.h>Operacja implementuje bramę Hadamard.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="4ce8c-146">Ta zmiana polega na tym, że Pauli $X $ i $Z $ osi docelowej qubit, takich jak $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ i $H \ket{+} = \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="4ce8c-147">Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` i odpowiada jednemu qubitemu jednostkom:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4ce8c-148">\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: obecnie jest to funkcja, która używa quadwhack.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4ce8c-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4ce8c-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4ce8c-150">Brama Hadamard jest szczególnie ważna, ponieważ może służyć do tworzenia nadpozycji {0} Stanów $ \ket $ i $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="4ce8c-151">W reprezentacji w sferze Bloch, najłatwiej jest traktować ją jako rotacja $ \ket{\psi} $ wokół osi x przez $ \pi $ RADIANS ($ 180 ^ \circ $), po której następuje rotacja (w prawo) wokół osi y przez $ \ pi/2 $ RADIANS ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="4ce8c-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Operacja Hadamard zamapowana na sferę Bloch](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="4ce8c-153"><xref:microsoft.quantum.intrinsic.s>Operacja implementuje bramę fazy $S $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="4ce8c-154">To jest pierwiastek kwadratowy macierzy Pauli $Z $ operacji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="4ce8c-155">Oznacza to, że $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="4ce8c-156">Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` i odpowiada jednemu qubitemu jednostkom:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4ce8c-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie używa to hakera quadwhack.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4ce8c-158">0 & i \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4ce8c-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="4ce8c-159">Rotacje</span><span class="sxs-lookup"><span data-stu-id="4ce8c-159">Rotations</span></span> ####

<span data-ttu-id="4ce8c-160">Oprócz operacji Pauli i Clifford powyżej, Q# Preludium oferuje różne sposoby wyrażania rotacji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="4ce8c-161">Zgodnie z opisem w [operacjach pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), możliwość rotacji jest niezwykle ważna dla algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="4ce8c-162">Zaczynamy od tego, że możemy wyrazić jakąkolwiek operację qubit za pomocą bram $H $ i $T $, gdzie $H $ jest operacją Hadamard, a gdzie \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie korzysta z platformy Quad back/Swagger/docs/v1..</span><span class="sxs-lookup"><span data-stu-id="4ce8c-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="4ce8c-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} to jest pierwiastek kwadratowy <xref:microsoft.quantum.intrinsic.s> operacji, na przykład $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="4ce8c-164">Brama $T $ jest zaimplementowana przez <xref:microsoft.quantum.intrinsic.t> operację i ma sygnaturę `(Qubit => Unit is Adj + Ctl)` wskazującą, że jest operacją jednostkową na jednym qubit.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="4ce8c-165">Mimo że jest to w zasadzie wystarczającej do opisywania dowolnej operacji pojedynczej qubit, różne maszyny docelowe mogą być bardziej wydajnymi reprezentacjami dla rotacji z operatorami Pauli, tak że Preludium zawiera różne sposoby convienentlynia takich rotacji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="4ce8c-166">Najbardziej podstawowe są <xref:microsoft.quantum.intrinsic.r> operacje, które implementują obrót wokół określonej osi Pauli, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} gdzie $ \sigma $ jest operatorem Pauli, $ \phi $ to kąt i gdzie $ \exp $ reprezentuje tablicę wykładniczą.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="4ce8c-167">Ma sygnaturę `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , gdzie pierwsze dwie części danych wejściowych reprezentują klasyczne argumenty $ \sigma $ i $ \phi $, które są niezbędne do określenia operatora jednostkowego $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="4ce8c-168">Firma Microsoft może częściowo zastosować $ \sigma $ i $ \phi $, aby uzyskać operację, której typem jest moduł jednostki pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="4ce8c-169">Na przykład `R(PauliZ, PI() / 4, _)` ma typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce8c-170"><xref:microsoft.quantum.intrinsic.r>Operacja dzieli kąt wejścia na 2 i mnoży ją przez-1.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="4ce8c-171">W przypadku $Z $ rotacji oznacza to, że $ \ket {0} $ eigenstate jest obrócona o $-\phi/$2, a $ \ket {1} $ eigenstate jest obrócona o $ \phi/$2, tak aby $ \ket {1} $ eigenstate został obrócony przez $ \phi $ względem elementu $ \ket {0} $ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="4ce8c-172">W szczególności oznacza to, że `T` `R(PauliZ, PI() / 8, _)` różnią się tylko nieistotną [fazą globalną](xref:microsoft.quantum.glossary#global-phase).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="4ce8c-173">Z tego powodu $T $ jest czasami znane jako brama $ \frac{\pi} {8} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="4ce8c-174">Należy również pamiętać, że obracanie wokół siebie `PauliI` powoduje zastosowanie globalnej fazy $ \phi/$2.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="4ce8c-175">Chociaż takie fazy nie mają znaczenia, jak zostało to zatwierdzono w [dokumentach koncepcyjnych](xref:microsoft.quantum.concepts.qubit), są one istotne dla kontrolowanych `PauliI` rotacji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="4ce8c-176">W ramach algorytmów Quantum często warto wyrazić rotację jako ułamki dyadic, takie jak $ \phi = \pi k/2 ^ n $ dla niektórych $k \In \mathbb{Z} $ i $n \In \mathbb{N} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="4ce8c-177"><xref:microsoft.quantum.intrinsic.rfrac>Operacja implementuje obrót wokół określonej osi Pauli przy użyciu tej Konwencji.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="4ce8c-178">Różni się od <xref:microsoft.quantum.intrinsic.r> , że kąt obrotu jest określony jako dwa dane wejściowe typu `Int` interpretowane jako ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="4ce8c-179">W tym celu `RFrac` ma sygnaturę `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-180">Implementuje qubit jednostki $ \exp (\pi k \sigma/2 ^ n) $, gdzie $ \sigma $ jest matrycą Pauli odpowiadającą pierwszemu argumentowi, $k $ jest drugim argumentem, a $n $ to trzeci argument.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="4ce8c-181">`RFrac(_,k,n,_)` jest taka sama jak `R(_,-πk/2^n,_)` ; należy zauważyć, że kąt jest *wartością ujemną* części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="4ce8c-182"><xref:microsoft.quantum.intrinsic.rx>Operacja implementuje obrót wokół osi Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="4ce8c-183">Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-184">`Rx(_, _)` jest taka sama jak `R(PauliX, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="4ce8c-185"><xref:microsoft.quantum.intrinsic.ry>Operacja implementuje obrót wokół osi Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="4ce8c-186">Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-187">`Ry(_, _)` jest taka sama jak `R(PauliY,_ , _)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="4ce8c-188"><xref:microsoft.quantum.intrinsic.rz>Operacja implementuje obrót wokół osi Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="4ce8c-189">Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-190">`Rz(_, _)` jest taka sama jak `R(PauliZ, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="4ce8c-191"><xref:microsoft.quantum.intrinsic.r1>Operacja implementuje obrót o podaną ilość około $ \ket {1} $, eigenstate $-$1 z $Z $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="4ce8c-192">Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-193">`R1(phi,_)` jest taka sama, jak `R(PauliZ,phi,_)` i `R(PauliI,-phi,_)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="4ce8c-194"><xref:microsoft.quantum.intrinsic.r1frac>Operacja implementuje rotację ułamkową o podaną ilość wokół elementu Z = 1 eigenstate.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="4ce8c-195">Ma sygnaturę `((Int,Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-196">`R1Frac(k,n,_)` jest taka sama, jak `RFrac(PauliZ,-k.n+1,_)` i `RFrac(PauliI,k,n+1,_)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="4ce8c-197">Poniżej przedstawiono przykład operacji obrotu (wokół osi Pauli $Z $, w tym wystąpieniu) zamapowanej na sferę Bloch:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Operacja obrotu zamapowana na Bloch sferę](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="4ce8c-199">Operacje wykonywane przez wiele qubit</span><span class="sxs-lookup"><span data-stu-id="4ce8c-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="4ce8c-200">Oprócz operacji pojedynczych qubit, Preludium także definiuje kilka operacji qubit.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="4ce8c-201">Po pierwsze, <xref:microsoft.quantum.intrinsic.cnot> operacja wykonuje standardowe kontrolowane `NOT` bramy, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 0 & \\ \\ 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="4ce8c-202">\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)` reprezentującą, że $ \operatorname{CNOT} $ działa unitarily na dwóch indywidualnych qubits.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="4ce8c-203">`CNOT(q1, q2)` jest taka sama jak `(Controlled X)([q1], q2)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="4ce8c-204">Ponieważ `Controlled` Funktor umożliwia kontrolę nad rejestrem, używamy literału tablicowego, `[q1]` Aby wskazać, że chcemy tylko jedną kontrolkę.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="4ce8c-205"><xref:microsoft.quantum.intrinsic.ccnot>Operacja wykonuje podwójnie sterowaną bramą, a także znaną jako bramę Toffoli.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="4ce8c-206">Ma sygnaturę `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-207">`CCNOT(q1, q2, q3)` jest taka sama jak `(Controlled X)([q1, q2], q3)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="4ce8c-208"><xref:microsoft.quantum.intrinsic.swap>Operacja zamienia Stany Quantum z dwóch qubitsów.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="4ce8c-209">Oznacza to, że implementuje macierz jednostkową \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 & & 1 \\ \\ & 0 & 0 \\ \\ 0 & 0 & 0 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="4ce8c-210">\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4ce8c-211">`SWAP(q1,q2)` jest odpowiednikiem `CNOT(q1, q2)` `CNOT(q2, q1)` , a następnie `CNOT(q1, q2)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce8c-212">Brama wymiany *nie* jest taka sama jak zmiana rozmieszczenia elementów zmiennej typu `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="4ce8c-213">Zastosowanie `SWAP(q1, q2)` powoduje zmianę stanu qubits, do którego odwołuje się `q1` i, i `q2` `let swappedRegister = [q2, q1];` tylko ma wpływ na sposób odwoływania się do tych qubits.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="4ce8c-214">Ponadto program `(Controlled SWAP)([q0], (q1, q2))` pozwala na `SWAP` spełnienie stanu qubit trzeciego, który nie może reprezentować przez ponowne rozmieszczenie elementów.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="4ce8c-215">Brama przełączenia kontrolowanego, znana także jako brama Fredkin, jest wystarczająco wydajna, aby obejmowała wszystkie klasyczne obliczenia.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="4ce8c-216">Na koniec Preludium zawiera dwie operacje do reprezentowania wykładniczych operatorów wieloqubitowych Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="4ce8c-217"><xref:microsoft.quantum.intrinsic.exp>Operacja wykonuje rotację na podstawie iloczynu Pauli macierzy. reprezentowane przez wieloqubitne \Begin{Equation} \operatorname{EXP} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} WHERE $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ jest sekwencją operatorów pojedyncze-qubit Pauli i gdzie $ \phi $ jest kątem.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="4ce8c-218">`Exp`Obrót reprezentuje element $ \vec{\sigma} $ jako tablicę `Pauli` elementów, tak że ma on sygnaturę `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4ce8c-219"><xref:microsoft.quantum.intrinsic.expfrac>Operacja wykonuje ten sam obrót przy użyciu notacji dyadic ułamek opisanej powyżej.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="4ce8c-220">Ma sygnaturę `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="4ce8c-221">Wartość wykładnicza iloczynu dwuczęściowego w operatorach Pauli nie jest taka sama jak iloczynów dwuczęściowych operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="4ce8c-222">Oznacza to, że $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="4ce8c-223">Miary</span><span class="sxs-lookup"><span data-stu-id="4ce8c-223">Measurements</span></span> ###

<span data-ttu-id="4ce8c-224">Podczas mierzenia, wartość + 1 eigenvalue operatora jest mierzona jako `Zero` wynik i-1 eigenvalue do `One` wyniku.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce8c-225">Chociaż ta konwencja może wydawać się nieparzysta, ma dwie zalety.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="4ce8c-226">Najpierw poszanowanie wyniku $ \ket {0} $ jest reprezentowane przez `Result` wartość `Zero` , natomiast przestrzeganie $ \ket {1} $ odpowiada `One` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="4ce8c-227">Następnie możemy napisać, że eigenvalue $ \lambda $ odpowiadający wynikowi $r $ to $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="4ce8c-228">Operacje pomiarów nie obsługują ani `Adjoint` `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="4ce8c-229"><xref:microsoft.quantum.intrinsic.measure>Operacja wykonuje wspólne pomiary co najmniej jednego qubits w określonym produkcie operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="4ce8c-230">Jeśli macierz Pauli i tablica qubit mają różne długości, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="4ce8c-231">`Measure` ma sygnaturę `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="4ce8c-232">Należy zauważyć, że wspólne pomiary nie są takie same jak pomiary każdego qubit indywidualnie.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="4ce8c-233">Rozważmy na przykład stan $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="4ce8c-234">Pomiary $Z _0 $ i $Z _1 $ osobno, uzyskujemy wyniki $r _0 = $1 i $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="4ce8c-235">Pomiar $Z _0 Z_1 $, jednak pobieramy pojedynczy wynik $r _ {\textrm{joint}}d = $0, co oznacza, że para wartości $ \ket {11} $ jest dodatnia.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="4ce8c-236">Umieść inaczej: $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="4ce8c-237">Ze względu na to, że pouczymy się *tylko* o tym, że dane z tego pomiaru są zgodne, wszystkie informacje o Quantum, reprezentowane w położeniu między stanem 2 2-qubit pozytywnej parzystości, $ \ket {00} $ i $ \ket {11} $, są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="4ce8c-238">Ta właściwość będzie istotna w przyszłości, ponieważ omawiamy korekcję błędów.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="4ce8c-239">Dla wygody Preludium również obejmuje dwie inne operacje do mierzenia qubits.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="4ce8c-240">Najpierw ponieważ wykonywanie pomiarów qubit jest dość popularne, Preludium definiuje skrót dla tego przypadku.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="4ce8c-241"><xref:microsoft.quantum.intrinsic.m>Operacja mierzy operator Pauli $Z $ na jednym qubit i ma sygnaturę `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="4ce8c-242">`M(q)` jest odpowiednikiem `Measure([PauliZ], [q])` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="4ce8c-243"><xref:microsoft.quantum.measurement.multim>Mierzy operator Pauli $Z $ *oddzielnie* na każdej tablicy qubits, zwracając *tablicę* `Result` wartości uzyskanych dla każdego qubit.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="4ce8c-244">W niektórych przypadkach może to być zoptymalizowane.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-244">In some cases this can be optimized.</span></span> <span data-ttu-id="4ce8c-245">Ma sygnaturę ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="4ce8c-246">`MultiM(qs)` jest równoważne:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="4ce8c-247">Funkcje i operacje rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="4ce8c-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="4ce8c-248">Ponadto Preludium definiuje bogaty zestaw funkcji konwersji matematycznych i typów na poziomie platformy .NET do użycia w Q# kodzie.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="4ce8c-249">Na przykład <xref:microsoft.quantum.math> przestrzeń nazw definiuje użyteczne operacje, takie jak <xref:microsoft.quantum.math.sin> i <xref:microsoft.quantum.math.log> .</span><span class="sxs-lookup"><span data-stu-id="4ce8c-249">For instance, the <xref:microsoft.quantum.math> namespace defines useful operations such as <xref:microsoft.quantum.math.sin> and <xref:microsoft.quantum.math.log>.</span></span>
<span data-ttu-id="4ce8c-250">Implementacja udostępniona przez zestaw Quantum Development Kit używa klasycznej biblioteki klas .NET, co może wiązać się z dodatkową komunikacją między programami Quantum i ich klasycznymi sterownikami.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="4ce8c-251">Chociaż nie ma to problemu dla lokalnego symulatora, może to być problem z wydajnością w przypadku korzystania z zdalnego symulatora lub rzeczywistego sprzętu jako maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="4ce8c-252">Ten sam komputer docelowy może wyeliminować ten wpływ na wydajność, zastępując te operacje niektórymi wersjami, które są bardziej wydajne dla danego systemu.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="4ce8c-253">Math</span><span class="sxs-lookup"><span data-stu-id="4ce8c-253">Math</span></span> ###

<span data-ttu-id="4ce8c-254"><xref:microsoft.quantum.math>Przestrzeń nazw zawiera wiele przydatnych funkcji z [ `System.Math` klasy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)podstawowej biblioteki klas programu .NET.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-254">The <xref:microsoft.quantum.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="4ce8c-255">Te funkcje mogą być używane w taki sam sposób jak inne Q# funkcje:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="4ce8c-256">Gdzie metoda statyczna platformy .NET została przeciążona na podstawie typu argumentów, odpowiadająca Q# Funkcja jest oznaczona sufiksem wskazującym typ danych wejściowych:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="4ce8c-257">Operacje bitowe</span><span class="sxs-lookup"><span data-stu-id="4ce8c-257">Bitwise Operations</span></span> ###

<span data-ttu-id="4ce8c-258">Na koniec <xref:microsoft.quantum.bitwise> przestrzeń nazw zapewnia kilka przydatnych funkcji manipulowania liczbami całkowitymi za pomocą operatorów bitowych.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-258">Finally, the <xref:microsoft.quantum.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="4ce8c-259">Na przykład <xref:microsoft.quantum.bitwise.parity> zwraca bitową parzystość liczby całkowitej jako inną liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-259">For instance, <xref:microsoft.quantum.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
