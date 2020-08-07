---
<span data-ttu-id="9a7e4-101">title: Opis platformy Quantum Oracle: informacje na temat pracy z i definiowania Quantum Oracle, operacje czarnego pola, które są używane jako dane wejściowe w innym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="9a7e4-102">Autor: cgranade UID: Microsoft. Quantum. koncepcje. Oracles MS. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 MS. temat: artykuł No-Loc:</span><span class="sxs-lookup"><span data-stu-id="9a7e4-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="9a7e4-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-103">"Q#"</span></span>
- <span data-ttu-id="9a7e4-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-104">"$$v"</span></span>
- <span data-ttu-id="9a7e4-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-105">"$$"</span></span>
- <span data-ttu-id="9a7e4-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-106">"$$"</span></span>
- <span data-ttu-id="9a7e4-107">"$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-107">"$"</span></span>
- <span data-ttu-id="9a7e4-108">"$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-108">"$"</span></span>
- <span data-ttu-id="9a7e4-109">"$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-109">"$"</span></span>
- <span data-ttu-id="9a7e4-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-110">"$$"</span></span>
- <span data-ttu-id="9a7e4-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-111">"\cdots"</span></span>
- <span data-ttu-id="9a7e4-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-112">"bmatrix"</span></span>
- <span data-ttu-id="9a7e4-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-113">"\ddots"</span></span>
- <span data-ttu-id="9a7e4-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-114">"\equiv"</span></span>
- <span data-ttu-id="9a7e4-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-115">"\sum"</span></span>
- <span data-ttu-id="9a7e4-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-116">"\begin"</span></span>
- <span data-ttu-id="9a7e4-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-117">"\end"</span></span>
- <span data-ttu-id="9a7e4-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-118">"\sqrt"</span></span>
- <span data-ttu-id="9a7e4-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-119">"\otimes"</span></span>
- <span data-ttu-id="9a7e4-120">"{"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-120">"{"</span></span>
- <span data-ttu-id="9a7e4-121">"}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-121">"}"</span></span>
- <span data-ttu-id="9a7e4-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-122">"\text"</span></span>
- <span data-ttu-id="9a7e4-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-123">"\phi"</span></span>
- <span data-ttu-id="9a7e4-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-124">"\kappa"</span></span>
- <span data-ttu-id="9a7e4-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-125">"\psi"</span></span>
- <span data-ttu-id="9a7e4-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-126">"\alpha"</span></span>
- <span data-ttu-id="9a7e4-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-127">"\beta"</span></span>
- <span data-ttu-id="9a7e4-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-128">"\gamma"</span></span>
- <span data-ttu-id="9a7e4-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-129">"\delta"</span></span>
- <span data-ttu-id="9a7e4-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-130">"\omega"</span></span>
- <span data-ttu-id="9a7e4-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-131">"\bra"</span></span>
- <span data-ttu-id="9a7e4-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-132">"\ket"</span></span>
- <span data-ttu-id="9a7e4-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-133">"\boldone"</span></span>
- <span data-ttu-id="9a7e4-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-134">"\\\\"</span></span>
- <span data-ttu-id="9a7e4-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-135">"\\"</span></span>
- <span data-ttu-id="9a7e4-136">"="</span><span class="sxs-lookup"><span data-stu-id="9a7e4-136">"="</span></span>
- <span data-ttu-id="9a7e4-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-137">"\frac"</span></span>
- <span data-ttu-id="9a7e4-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-138">"\text"</span></span>
- <span data-ttu-id="9a7e4-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-139">"\mapsto"</span></span>
- <span data-ttu-id="9a7e4-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-140">"\dagger"</span></span>
- <span data-ttu-id="9a7e4-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-141">"\to"</span></span>
- <span data-ttu-id="9a7e4-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-142">"\begin{cases}"</span></span>
- <span data-ttu-id="9a7e4-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-143">"\end{cases}"</span></span>
- <span data-ttu-id="9a7e4-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-144">"\operatorname"</span></span>
- <span data-ttu-id="9a7e4-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-145">"\braket"</span></span>
- <span data-ttu-id="9a7e4-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-146">"\id"</span></span>
- <span data-ttu-id="9a7e4-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-147">"\expect"</span></span>
- <span data-ttu-id="9a7e4-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-148">"\defeq"</span></span>
- <span data-ttu-id="9a7e4-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-149">"\variance"</span></span>
- <span data-ttu-id="9a7e4-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-150">"\dd"</span></span>
- <span data-ttu-id="9a7e4-151">"&"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-151">"&"</span></span>
- <span data-ttu-id="9a7e4-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-152">"\begin{align}"</span></span>
- <span data-ttu-id="9a7e4-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-153">"\end{align}"</span></span>
- <span data-ttu-id="9a7e4-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-154">"\Lambda"</span></span>
- <span data-ttu-id="9a7e4-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-155">"\lambda"</span></span>
- <span data-ttu-id="9a7e4-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-156">"\Omega"</span></span>
- <span data-ttu-id="9a7e4-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-157">"\mathrm"</span></span>
- <span data-ttu-id="9a7e4-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-158">"\left"</span></span>
- <span data-ttu-id="9a7e4-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-159">"\right"</span></span>
- <span data-ttu-id="9a7e4-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-160">"\qquad"</span></span>
- <span data-ttu-id="9a7e4-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-161">"\times"</span></span>
- <span data-ttu-id="9a7e4-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-162">"\big"</span></span>
- <span data-ttu-id="9a7e4-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-163">"\langle"</span></span>
- <span data-ttu-id="9a7e4-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-164">"\rangle"</span></span>
- <span data-ttu-id="9a7e4-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-165">"\bigg"</span></span>
- <span data-ttu-id="9a7e4-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-166">"\Big"</span></span>
- <span data-ttu-id="9a7e4-167">"|"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-167">"|"</span></span>
- <span data-ttu-id="9a7e4-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-168">"\mathbb"</span></span>
- <span data-ttu-id="9a7e4-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-169">"\vec"</span></span>
- <span data-ttu-id="9a7e4-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-170">"\in"</span></span>
- <span data-ttu-id="9a7e4-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-171">"\texttt"</span></span>
- <span data-ttu-id="9a7e4-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-172">"\ne"</span></span>
- <span data-ttu-id="9a7e4-173">"<"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-173">"<"</span></span>
- <span data-ttu-id="9a7e4-174">">"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-174">">"</span></span>
- <span data-ttu-id="9a7e4-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-175">"\leq"</span></span>
- <span data-ttu-id="9a7e4-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-176">"\geq"</span></span>
- <span data-ttu-id="9a7e4-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-177">"~~"</span></span>
- <span data-ttu-id="9a7e4-178">"~"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-178">"~"</span></span>
- <span data-ttu-id="9a7e4-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="9a7e4-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="9a7e4-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="9a7e4-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="9a7e4-182">Bazy danych Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="9a7e4-182">Quantum Oracles</span></span>

<span data-ttu-id="9a7e4-183">Oracle $ O $ to operacja "czarna Box", która jest używana jako dane wejściowe w innym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="9a7e4-184">Często takie operacje są definiowane przy użyciu funkcji klasycznej $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m, $ która przyjmuje $ n $ -bitowe dane binarne danych binarnych i tworzy $ $ mikrobitowe dane wyjściowe binarne.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="9a7e4-185">W tym celu należy wziąć pod uwagę określony kod binarny $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="9a7e4-186">Możemy etykietować Stany qubit jako $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="9a7e4-187">Możemy najpierw spróbować zdefiniować $ o tak, aby $ $ o \ket { x } = \ket { f (x) } $ , ale wystąpiło kilka problemów.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="9a7e4-188">Po pierwsze, $ f $ może mieć inny rozmiar danych wejściowych i wyjściowych ( $ n \ne m $ ), co oznacza, że zastosowanie $ $ w programie spowoduje zmianę liczby qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="9a7e4-189">Sekunda, nawet jeśli $ n = m $ , funkcja nie może być odwracalna: Jeśli $ f (x) = f (y) $ dla niektórych $ x \ne y $ , następnie $ o \ket { x } = o \ket { y, } $ ale $ o ^ \dagger o x o ^ o \ket { } \ne \dagger \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="9a7e4-190">Oznacza to, że nie będzie można skonstruować operacji sąsiedniej $ O ^ \dagger $ , a firmy Oracle muszą mieć dla nich przyległych.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="9a7e4-191">Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="9a7e4-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="9a7e4-192">Firma Microsoft może zająć się obydwoma problemami, wprowadzając drugi rejestr $ m $ qubits do przechowywania odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="9a7e4-193">Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $ x \in \\ { 0, 1 \\ } ^ n $ i $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="9a7e4-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="9a7e4-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="9a7e4-195">Teraz $ o = ^ \dagger $ przez konstrukcję, dlatego zostały rozwiązane oba poprzednie problemy.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="9a7e4-196">>Aby zobaczyć, że o $ = godzinie "o ^" { \dagger } $ , należy pamiętać, że $ ^ 2 = \boldone $ od $ \oplus b \oplus b = a $ dla wszystkich $ a, b \in \: :: No-Loc ({)::: 0, 1 \: :: No-Loc (})::: $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="9a7e4-197">>W związku z tym $ o \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="9a7e4-198">Ważną kwestią jest zdefiniowanie Oracle w ten sposób w przypadku każdego stanu podstawy obliczeniowej $ \ket { x y, a } \ket { } $ także zdefiniowanie $ $ działań dla każdego innego stanu.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="9a7e4-199">Następuje to bezpośrednio od faktu $ , że $ , podobnie jak wszystkie operacje Quantum, jest liniowy w stanie, w którym działa.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="9a7e4-200">Rozważmy operację Hadamard, na przykład, która jest zdefiniowana przez $ h \ket { 0 } = \ket { + } $ i $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="9a7e4-201">Jeśli chcemy dowiedzieć się $ , jak h $ działa $ \ket { + } $ , można użyć tej $ godziny $ , która jest liniowa,</span><span class="sxs-lookup"><span data-stu-id="9a7e4-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="9a7e4-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="9a7e4-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="9a7e4-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="9a7e4-204">W przypadku definiowania naszej firmy Oracle $ O $ można w podobny sposób wykorzystać, że każdy stan $ \ket { \psi } $ na $ n + m $ qubits można napisać jako</span><span class="sxs-lookup"><span data-stu-id="9a7e4-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="9a7e4-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="9a7e4-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="9a7e4-206">gdzie $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ reprezentuje współczynniki stanu $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="9a7e4-207">Tak więc,</span><span class="sxs-lookup"><span data-stu-id="9a7e4-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="9a7e4-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="9a7e4-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="9a7e4-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="9a7e4-210">Fazy Oracle</span><span class="sxs-lookup"><span data-stu-id="9a7e4-210">Phase oracles</span></span>
<span data-ttu-id="9a7e4-211">Alternatywnie możemy kodować program $ f $ do programu Oracle $ o, $ stosując _fazę_ w oparciu o dane wejściowe $ $ . Można na przykład określić, $ $ że$$</span><span class="sxs-lookup"><span data-stu-id="9a7e4-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="9a7e4-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="9a7e4-213">Jeśli faza Oracle działa na bieżąco z rejestrem w stanie obliczenia $ \ket { x } $ , wówczas ta faza jest globalnym etapem i dlatego nie jest zauważalna.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="9a7e4-214">Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="9a7e4-215">Rozważmy na przykład fazę $ O_f firmy Oracle $ dla funkcji pojedynczej qubit $ f $ .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="9a7e4-216">Następnie$$</span><span class="sxs-lookup"><span data-stu-id="9a7e4-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="9a7e4-217">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="9a7e4-217">O_f \ket{+}</span></span>
        <span data-ttu-id="9a7e4-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="9a7e4-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="9a7e4-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="9a7e4-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="9a7e4-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="9a7e4-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="9a7e4-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="9a7e4-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="9a7e4-222">Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="9a7e4-223">Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="9a7e4-224">Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.</span><span class="sxs-lookup"><span data-stu-id="9a7e4-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="9a7e4-225">Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="9a7e4-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
