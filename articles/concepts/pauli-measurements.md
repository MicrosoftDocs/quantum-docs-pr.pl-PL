---
<span data-ttu-id="e565d-101">title: Paulis Description: informacje na temat pracy z operacjami pomiaru pojedynczego i wieloqubitowego Pauli.</span><span class="sxs-lookup"><span data-stu-id="e565d-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="e565d-102">Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Pauli MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:</span><span class="sxs-lookup"><span data-stu-id="e565d-102">author: QuantumWriter uid: microsoft.quantum.concepts.pauli ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="e565d-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="e565d-103">"Q#"</span></span>
- <span data-ttu-id="e565d-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="e565d-104">"$$v"</span></span>
- <span data-ttu-id="e565d-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="e565d-105">"$$"</span></span>
- <span data-ttu-id="e565d-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="e565d-106">"$$"</span></span>
- <span data-ttu-id="e565d-107">"$"</span><span class="sxs-lookup"><span data-stu-id="e565d-107">"$"</span></span>
- <span data-ttu-id="e565d-108">"$"</span><span class="sxs-lookup"><span data-stu-id="e565d-108">"$"</span></span>
- <span data-ttu-id="e565d-109">"$"</span><span class="sxs-lookup"><span data-stu-id="e565d-109">"$"</span></span>
- <span data-ttu-id="e565d-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="e565d-110">"$$"</span></span>
- <span data-ttu-id="e565d-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="e565d-111">"\cdots"</span></span>
- <span data-ttu-id="e565d-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="e565d-112">"bmatrix"</span></span>
- <span data-ttu-id="e565d-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="e565d-113">"\ddots"</span></span>
- <span data-ttu-id="e565d-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="e565d-114">"\equiv"</span></span>
- <span data-ttu-id="e565d-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="e565d-115">"\sum"</span></span>
- <span data-ttu-id="e565d-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="e565d-116">"\begin"</span></span>
- <span data-ttu-id="e565d-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="e565d-117">"\end"</span></span>
- <span data-ttu-id="e565d-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="e565d-118">"\sqrt"</span></span>
- <span data-ttu-id="e565d-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="e565d-119">"\otimes"</span></span>
- <span data-ttu-id="e565d-120">"{"</span><span class="sxs-lookup"><span data-stu-id="e565d-120">"{"</span></span>
- <span data-ttu-id="e565d-121">"}"</span><span class="sxs-lookup"><span data-stu-id="e565d-121">"}"</span></span>
- <span data-ttu-id="e565d-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="e565d-122">"\text"</span></span>
- <span data-ttu-id="e565d-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="e565d-123">"\phi"</span></span>
- <span data-ttu-id="e565d-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="e565d-124">"\kappa"</span></span>
- <span data-ttu-id="e565d-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="e565d-125">"\psi"</span></span>
- <span data-ttu-id="e565d-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="e565d-126">"\alpha"</span></span>
- <span data-ttu-id="e565d-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="e565d-127">"\beta"</span></span>
- <span data-ttu-id="e565d-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="e565d-128">"\gamma"</span></span>
- <span data-ttu-id="e565d-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="e565d-129">"\delta"</span></span>
- <span data-ttu-id="e565d-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="e565d-130">"\omega"</span></span>
- <span data-ttu-id="e565d-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="e565d-131">"\bra"</span></span>
- <span data-ttu-id="e565d-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="e565d-132">"\ket"</span></span>
- <span data-ttu-id="e565d-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="e565d-133">"\boldone"</span></span>
- <span data-ttu-id="e565d-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="e565d-134">"\\\\"</span></span>
- <span data-ttu-id="e565d-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="e565d-135">"\\"</span></span>
- <span data-ttu-id="e565d-136">"="</span><span class="sxs-lookup"><span data-stu-id="e565d-136">"="</span></span>
- <span data-ttu-id="e565d-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="e565d-137">"\frac"</span></span>
- <span data-ttu-id="e565d-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="e565d-138">"\text"</span></span>
- <span data-ttu-id="e565d-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="e565d-139">"\mapsto"</span></span>
- <span data-ttu-id="e565d-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="e565d-140">"\dagger"</span></span>
- <span data-ttu-id="e565d-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="e565d-141">"\to"</span></span>
- <span data-ttu-id="e565d-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="e565d-142">"\begin{cases}"</span></span>
- <span data-ttu-id="e565d-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="e565d-143">"\end{cases}"</span></span>
- <span data-ttu-id="e565d-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="e565d-144">"\operatorname"</span></span>
- <span data-ttu-id="e565d-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="e565d-145">"\braket"</span></span>
- <span data-ttu-id="e565d-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="e565d-146">"\id"</span></span>
- <span data-ttu-id="e565d-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="e565d-147">"\expect"</span></span>
- <span data-ttu-id="e565d-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="e565d-148">"\defeq"</span></span>
- <span data-ttu-id="e565d-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="e565d-149">"\variance"</span></span>
- <span data-ttu-id="e565d-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="e565d-150">"\dd"</span></span>
- <span data-ttu-id="e565d-151">"&"</span><span class="sxs-lookup"><span data-stu-id="e565d-151">"&"</span></span>
- <span data-ttu-id="e565d-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="e565d-152">"\begin{align}"</span></span>
- <span data-ttu-id="e565d-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="e565d-153">"\end{align}"</span></span>
- <span data-ttu-id="e565d-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="e565d-154">"\Lambda"</span></span>
- <span data-ttu-id="e565d-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="e565d-155">"\lambda"</span></span>
- <span data-ttu-id="e565d-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="e565d-156">"\Omega"</span></span>
- <span data-ttu-id="e565d-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="e565d-157">"\mathrm"</span></span>
- <span data-ttu-id="e565d-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="e565d-158">"\left"</span></span>
- <span data-ttu-id="e565d-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="e565d-159">"\right"</span></span>
- <span data-ttu-id="e565d-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="e565d-160">"\qquad"</span></span>
- <span data-ttu-id="e565d-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="e565d-161">"\times"</span></span>
- <span data-ttu-id="e565d-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="e565d-162">"\big"</span></span>
- <span data-ttu-id="e565d-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="e565d-163">"\langle"</span></span>
- <span data-ttu-id="e565d-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="e565d-164">"\rangle"</span></span>
- <span data-ttu-id="e565d-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="e565d-165">"\bigg"</span></span>
- <span data-ttu-id="e565d-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="e565d-166">"\Big"</span></span>
- <span data-ttu-id="e565d-167">"|"</span><span class="sxs-lookup"><span data-stu-id="e565d-167">"|"</span></span>
- <span data-ttu-id="e565d-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="e565d-168">"\mathbb"</span></span>
- <span data-ttu-id="e565d-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="e565d-169">"\vec"</span></span>
- <span data-ttu-id="e565d-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="e565d-170">"\in"</span></span>
- <span data-ttu-id="e565d-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="e565d-171">"\texttt"</span></span>
- <span data-ttu-id="e565d-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="e565d-172">"\ne"</span></span>
- <span data-ttu-id="e565d-173">"<"</span><span class="sxs-lookup"><span data-stu-id="e565d-173">"<"</span></span>
- <span data-ttu-id="e565d-174">">"</span><span class="sxs-lookup"><span data-stu-id="e565d-174">">"</span></span>
- <span data-ttu-id="e565d-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="e565d-175">"\leq"</span></span>
- <span data-ttu-id="e565d-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="e565d-176">"\geq"</span></span>
- <span data-ttu-id="e565d-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="e565d-177">"~~"</span></span>
- <span data-ttu-id="e565d-178">"~"</span><span class="sxs-lookup"><span data-stu-id="e565d-178">"~"</span></span>
- <span data-ttu-id="e565d-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e565d-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="e565d-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e565d-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="e565d-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="e565d-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="e565d-182">Pomiary Pauli</span><span class="sxs-lookup"><span data-stu-id="e565d-182">Pauli Measurements</span></span>

<span data-ttu-id="e565d-183">W poprzednich dyskusjach koncentrujemy się na obliczaniu pomiarów bazowych.</span><span class="sxs-lookup"><span data-stu-id="e565d-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="e565d-184">W rzeczywistości istnieją inne typowe pomiary związane z przetwarzaniem jednostek Quantum, które z perspektywy notacji są wygodne do wyrażania na podstawie obliczeniowych pomiarów.</span><span class="sxs-lookup"><span data-stu-id="e565d-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="e565d-185">Podczas pracy z programem Q# najbardziej typowym rodzajem pomiarów, w których będziesz korzystać, będzie prawdopodobnie *Pauli pomiary*, które uogólnią pomiary bazowe, aby uwzględnić pomiary w innych bazach i o parzystości między różnymi qubits.</span><span class="sxs-lookup"><span data-stu-id="e565d-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="e565d-186">W takich przypadkach często omawia się pomiar pomiaru operatora Pauli, w ogólności operatora, takiego jak $ X, Y, Z $ lub $ z \otimes z, x \otimes x, x \otimes Y $ i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="e565d-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="e565d-187">> W programie Q# Operatory qubit Pauli są ogólnie reprezentowane przez tablice typu `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="e565d-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="e565d-188">> Na przykład, aby reprezentować $ X \otimes Z \otimes Y $ , można użyć tablicy `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="e565d-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="e565d-189">Omawianie pomiaru w warunkach operatorów Pauli jest szczególnie powszechne w podpolu korekcji błędów Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="e565d-190">W programie Q# przestrzegamy podobnej Konwencji. teraz wyjaśnimy ten alternatywny widok pomiarów.</span><span class="sxs-lookup"><span data-stu-id="e565d-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="e565d-191">Przed napisaniem szczegółowych informacji o tym, jak sądzisz o pomiarze Pauli, warto zastanowić się nad tym, co mierzy jeden qubit wewnątrz komputera Quantum w stanie Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="e565d-192">Wyobraź sobie, że mamy $ $ stan qubit Quantum, a następnie przemierzenie jednego qubit natychmiast $ $ wystawia 2 ^ n możliwości, które mogą znajdować się w stanie.</span><span class="sxs-lookup"><span data-stu-id="e565d-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="e565d-193">Innymi słowy, pomiar projektuje stan Quantum na jedną z dwóch miejsc.</span><span class="sxs-lookup"><span data-stu-id="e565d-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="e565d-194">Możemy uogólnić sposób, w jaki myślimy o pomiarach, aby odzwierciedlić ten Intuition.</span><span class="sxs-lookup"><span data-stu-id="e565d-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="e565d-195">Aby zwięzłie zidentyfikować te podobszary, należy zapoznać się z językiem.</span><span class="sxs-lookup"><span data-stu-id="e565d-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="e565d-196">Jednym ze sposobów opisywania dwóch podobszarów jest określenie ich za pośrednictwem macierzy, która ma dwie unikalne eigenvalues, podejmowane przez Konwencję do $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="e565d-197">Aby zapoznać się z prostym przykładem opisywania podobszarów w ten sposób, weź pod uwagę $ $ :</span><span class="sxs-lookup"><span data-stu-id="e565d-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="e565d-198">Z & = \begin{bmatrix} 1 & 0 \\\\ & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e565d-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="e565d-199">Odczytując elementy ukośne macierzy Pauli- $ Z $ , zobaczymy, że $ z $ ma dwa eigenvectors, $ \ket { 0 } $ i $ \ket { 1 } $ , z odpowiednimi eigenvalues $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="e565d-200">W takim przypadku, jeśli mierzę qubit i uzyskamy wartość `Zero` (odpowiadającą stanowi $ \ket { 0 } $ ), wiemy, że stan naszego qubitu to $ + 1 $ eigenstate $ $ operatora z.</span><span class="sxs-lookup"><span data-stu-id="e565d-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="e565d-201">Podobnie, jeśli uzyskamy `One` , wiemy, że stan naszego qubit to $ -1 $ eigenstate z $ $ . Ten proces jest określany w języku Pauli pomiarów jako "pomiar Pauli $ Z $ i" jest całkowicie równoważny do wykonywania obliczeń bazowych.</span><span class="sxs-lookup"><span data-stu-id="e565d-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="e565d-202">Każda $ 2 \times 2 $ macierz, która jest przekształceniem jednostkowym z $ z $ również spełnia te kryteria.</span><span class="sxs-lookup"><span data-stu-id="e565d-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="e565d-203">Oznacza to, że możemy również użyć macierzy $ a = u ^ \dagger z u $ , gdzie $ u $ jest dowolną inną macierzą jednostkową, aby uzyskać macierz, która definiuje dwa wyniki pomiaru w $ \Pm 1 $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="e565d-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="e565d-204">Notacja Pauliu odwołuje się do tej równoważności jednostki, identyfikując wartości $ X, Y, z, $ jako równoważne pomiary, które można wykonać, aby uzyskać informacje z qubit.</span><span class="sxs-lookup"><span data-stu-id="e565d-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="e565d-205">Te pomiary są podane poniżej dla wygody.</span><span class="sxs-lookup"><span data-stu-id="e565d-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="e565d-206">|Przekształcenie  | jednostek miary Pauli  |</span><span class="sxs-lookup"><span data-stu-id="e565d-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="e565d-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="e565d-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="e565d-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="e565d-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="e565d-209">|$ $ T | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="e565d-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="e565d-210">Oznacza to, że przy użyciu tego języka "pomiar $ Y $ " jest odpowiednikiem zastosowania $ HS ^ \dagger $ , a następnie mierzenia w oparciu o obliczenia, gdzie [`S`](xref:microsoft.quantum.intrinsic.s) jest wewnętrzną operacją Quantum czasami nazywaną "bramą fazowy" i może być symulowana przez macierz jednostkową</span><span class="sxs-lookup"><span data-stu-id="e565d-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="e565d-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e565d-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="e565d-212">1 & 0 \\\\ & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e565d-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="e565d-213">Jest również odpowiednikiem zastosowania $ HS ^ \dagger $ do wektora stanu Quantum, a następnie mierzenia $ z $ , tak że Następująca operacja jest równoważna z `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="e565d-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="e565d-214">Prawidłowy stan można znaleźć w wyniku przekształcenia z powrotem do podstawy obliczeniowej, co oznacza, $ że zastosowanie SH $ do wektora stanu Quantum; w powyższym fragmencie kodu przekształcenie z powrotem do podstawy obliczeniowej jest obsługiwane automatycznie przez użycie `within … apply` bloku.</span><span class="sxs-lookup"><span data-stu-id="e565d-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="e565d-215">W programie Q# Załóżmy, że wyniki---, czyli klasyczne informacje wyodrębnione ze stanu współdziałania ze stanem---są podawane przez `Result` wartość $ j \in \\ { \texttt { zero } , \texttt { jeden wskazuje, } \\ } $ czy wynik jest w $ (-1) ^ j $ eigenspace operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="e565d-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="e565d-216">Pomiary z wieloma qubitami</span><span class="sxs-lookup"><span data-stu-id="e565d-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="e565d-217">Pomiary operatorów Pauli wieloqubitowych są zdefiniowane w podobny sposób, jak pokazano w:</span><span class="sxs-lookup"><span data-stu-id="e565d-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="e565d-218">Z \otimes z 1 1,0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.</span><span class="sxs-lookup"><span data-stu-id="e565d-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="e565d-219">W ten sposób produkty dwuetapowe z dwóch $ operatorów Pauli-Z $ tworzą macierz składającą się z dwóch spacji składających się z $ + 1 $ i $ -1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="e565d-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="e565d-220">Podobnie jak w przypadku pojedynczej qubit, oba stanowią pół obszaru, co połowa dostępnego miejsca wektorowego należy do $ + 1 $ eigenspace i pozostałe połowy do $ -1 $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="e565d-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="e565d-221">Ogólnie rzecz biorąc, można łatwo zapoznać się z definicją iloczynu dwuczęściowego, któremu każdy dwuczęściowy iloczyn $ operatorów Pauli-z $ i tożsamość również przestrzega tego.</span><span class="sxs-lookup"><span data-stu-id="e565d-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="e565d-222">Przykład:</span><span class="sxs-lookup"><span data-stu-id="e565d-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="e565d-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e565d-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="e565d-224">1 & 0 & 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="e565d-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="e565d-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="e565d-227">0 &  0 & & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e565d-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="e565d-228">Tak jak wcześniej, każda jednostkowa transformacja takich macierzy również opisuje dwie spacje oznaczone przez $ \Pm 1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="e565d-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="e565d-229">Na przykład $ x \otimes x = h \otimes h (z \otimes z) h h \otimes $  od tożsamości z $ = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="e565d-230">Podobnie jak w przypadku pojedynczej qubit, wszystkie dwie qubit Pauli-pomiary mogą być zapisywane jako $ u ^ \dagger (Z \otimes \id ) u $ dla $ 4 \times 4 $ macierzy jednostkowych $ U $ . Wyliczmy przekształcenia w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e565d-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="e565d-231">>W poniższej tabeli użyto $ \operatorname { zamiany } $ do wskazania macierzy >$$</span><span class="sxs-lookup"><span data-stu-id="e565d-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="e565d-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e565d-232">> \begin{align}</span></span>
<span data-ttu-id="e565d-233">>     \operatorname{Zamień } &=</span><span class="sxs-lookup"><span data-stu-id="e565d-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="e565d-234">>     \left( \begin { macierz}</span><span class="sxs-lookup"><span data-stu-id="e565d-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="e565d-235">>1 & 0 & 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="e565d-236">>0 & 0 & 1 &\\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="e565d-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="e565d-238">>0 & 0 & z & 1 > \end { macierzy } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="e565d-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="e565d-239">> $$</span><span class="sxs-lookup"><span data-stu-id="e565d-239">> $$</span></span>
<span data-ttu-id="e565d-240">> służy do symulowania operacji wewnętrznej [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="e565d-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="e565d-241">|Przekształcenie     | jednostek miary Pauli  |</span><span class="sxs-lookup"><span data-stu-id="e565d-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="e565d-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="e565d-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="e565d-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="e565d-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="e565d-244">|$ \otimes \boldone T $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="e565d-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="e565d-245">|$\boldone \otimes Z $ | $ \operatorname { wymiany } Z $|</span><span class="sxs-lookup"><span data-stu-id="e565d-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="e565d-246">|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { Zamień } $|</span><span class="sxs-lookup"><span data-stu-id="e565d-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="e565d-247">|$\boldone \otimes t $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { swap } $|</span><span class="sxs-lookup"><span data-stu-id="e565d-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="e565d-248">|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="e565d-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="e565d-249">|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="e565d-250">|$T \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="e565d-251">|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="e565d-252">|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="e565d-253">|$T \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="e565d-254">|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="e565d-255">|$X \otimes T $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="e565d-256">|$T \otimes T $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="e565d-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="e565d-257">W tym miejscu [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operacja zostanie wyświetlona z następującej przyczyny.</span><span class="sxs-lookup"><span data-stu-id="e565d-257">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="e565d-258">Każda miara Pauli, która nie obejmuje macierzy, jest równoważna z jednostką z z z z z $ \boldone $ $ \otimes $ powyższym powodem.</span><span class="sxs-lookup"><span data-stu-id="e565d-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="e565d-259">Eigenvalues z z z z z i $ \otimes $ zależą od parzystości qubits, która składa się z każdego wektora obliczeniowego, a operacje kontrolowane nie służą do obliczenia tej parzystości i zapisania jej w pierwszym bitach.</span><span class="sxs-lookup"><span data-stu-id="e565d-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="e565d-260">Następnie po przemierzeniu pierwszego bitu możemy odzyskać tożsamość wynikowego, który jest równoważny do mierzenia operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="e565d-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="e565d-261">Jedna dodatkowa Uwaga: Chociaż może być skłonny do założenia, że pomiary $ z \otimes z z $ są takie same jak pomiary $ z \otimes \mathbb { 1 } $ i 1 $ \mathbb { } \otimes z $ , to założenie będzie miało wartość false.</span><span class="sxs-lookup"><span data-stu-id="e565d-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="e565d-262">Powodem jest to, że pomiar z projektów z z z $ \otimes $ jest stanem Quantum do $ $ eigenstate tych operatorów + 1 lub $ -1 $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="e565d-263">Pomiar $ z \otimes \mathbb { 1 } $ , a następnie $ \mathbb { 1 } \otimes z $ projektów w wektorze stanu Quantum najpierw do połowy miejsca z 1 $ \otimes \mathbb { } $ , a następnie do połowy miejsca $ \mathbb { 1 } \otimes z $ . Ponieważ istnieją cztery wektory obliczeniowe, przeprowadzenie obydwu pomiarów zmniejsza stan do kwartału, a tym samym redukuje go do jednego wektora obliczanego na podstawie.</span><span class="sxs-lookup"><span data-stu-id="e565d-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="e565d-264">Korelacje między qubits</span><span class="sxs-lookup"><span data-stu-id="e565d-264">Correlations between qubits</span></span>
<span data-ttu-id="e565d-265">Innym sposobem na pomiar iloczynów ilościowych macierzy Pauli, takich jak $ x \otimes x $ lub $ z \otimes z $ , jest to, że pomiary umożliwiają przeszukanie informacji przechowywanych w korelacji między tymi dwoma qubits.</span><span class="sxs-lookup"><span data-stu-id="e565d-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="e565d-266">Pomiar $ X \otimes \id $ pozwala przeglądać informacje, które są przechowywane lokalnie w pierwszej qubit.</span><span class="sxs-lookup"><span data-stu-id="e565d-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="e565d-267">Mimo że oba typy pomiarów są równie cenne w przypadku obliczeń opartych na usługach Quantum</span><span class="sxs-lookup"><span data-stu-id="e565d-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="e565d-268">Wykaże, że w ramach przetwarzania Quantum, często informacje, które chcesz poznać nie są przechowywane w żadnym z pojedynczych qubitów, ale raczej są przechowywane nielokalnie we wszystkich qubitsach i dlatego tylko przez ich przechodzenie przez wspólne pomiary (np. $ z \otimes $ ) czy te informacje stają się manifestem.</span><span class="sxs-lookup"><span data-stu-id="e565d-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="e565d-269">Na przykład w przypadku korekcji błędów często chcemy dowiedzieć się, jaki błąd wystąpił podczas uczenia niczego o stanie, który próbujesz chronić.</span><span class="sxs-lookup"><span data-stu-id="e565d-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="e565d-270">[Przykładowy kod przerzucania bitów](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) pokazuje przykład sposobu, w jaki można to zrobić przy użyciu pomiarów, takich jak z z i z z $ \otimes \otimes \id $ $ \id \otimes \otimes $ . < ! --Do zrobienia: Zmień tę wartość na link do przeglądarki przykładów, gdy tylko próbka kodu przerzucania bitów jest włączona.</span><span class="sxs-lookup"><span data-stu-id="e565d-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="e565d-271">Można również mierzyć dowolne operatory Pauli, takie jak $ X \otimes Y \otimes Z \otimes \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="e565d-272">Wszystkie te produkty dwubajtowe operatorów Pauli mają tylko dwa eigenvalues $ \Pm 1 $ i oba eigenspaces stanowią pół miejsca całego obszaru wektora.</span><span class="sxs-lookup"><span data-stu-id="e565d-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="e565d-273">W ten sposób są one zgodne z wymaganiami określonymi powyżej.</span><span class="sxs-lookup"><span data-stu-id="e565d-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="e565d-274">W Q# , takie pomiary zwracają $ wartość j, $ Jeśli pomiar daje wynik w eigenspace znaku $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="e565d-275">Pauli pomiary jako wbudowaną funkcję w programie Q# są przydatne, ponieważ pomiary takich operatorów wymagają długich łańcuchów kontrolowanych bram, a przekształcenia podstawowe, aby opisać bramę diagonalizing U, która jest $ $ wymagana do realizacji operacji jako iloczyn dwuskładnikowy z $ $ i $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="e565d-276">Aby określić, że chcesz wykonać jedną z tych wstępnie zdefiniowanych pomiarów, nie musisz martwić się o to, jak przekształcić swoją podstawę, tak aby pomiar bazowy obliczał informacje.</span><span class="sxs-lookup"><span data-stu-id="e565d-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="e565d-277">Q# obsługuje automatycznie wszystkie wymagane przekształcenia podstawowe.</span><span class="sxs-lookup"><span data-stu-id="e565d-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="e565d-278">Aby uzyskać więcej informacji, zobacz [`Measure`](xref:microsoft.quantum.intrinsic.measure) i [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operacje.</span><span class="sxs-lookup"><span data-stu-id="e565d-278">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="e565d-279">Theorem bez klonowania</span><span class="sxs-lookup"><span data-stu-id="e565d-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="e565d-280">Informacje o Quantum są zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="e565d-280">Quantum information is powerful.</span></span>
<span data-ttu-id="e565d-281">Umożliwia nam wykonywanie niezwykłych rzeczy, takich jak liczba czynników, które są wykładniczo szybsze niż najlepsze znane klasyczne algorytmy, lub efektywnie symuluje skorelowane systemy elektronów, które w sposób klasyczny wymagają wykładniczego kosztu, aby symulować dokładne symulacje.</span><span class="sxs-lookup"><span data-stu-id="e565d-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="e565d-282">Istnieją jednak ograniczenia dotyczące mocy obliczeniowej Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="e565d-283">Takie ograniczenie jest określone przez *theorem bez klonowania*.</span><span class="sxs-lookup"><span data-stu-id="e565d-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="e565d-284">Theorem No-kloning ma nazwę aptly.</span><span class="sxs-lookup"><span data-stu-id="e565d-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="e565d-285">Nie zezwala na klonowanie ogólnych Stanów Quantum przez komputer Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="e565d-286">Potwierdzenie theorem jest niezwykle proste.</span><span class="sxs-lookup"><span data-stu-id="e565d-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="e565d-287">Gdy Pełna weryfikacja theorem nie jest w stanie nieco zbyt technicznym w naszej dyskusji, w przypadku braku dodatkowych qubits pomocniczych znajduje się w naszym zakresie (pomocnicze qubits to qubits używany do wyznaczania miejsca podczas obliczeń i są łatwe w użyciu i zarządzane w programie Q# ). [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)</span><span class="sxs-lookup"><span data-stu-id="e565d-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="e565d-288">W przypadku takiego komputera z systemem Quantum Operacja klonowania musi być opisana przez macierz jednostkową.</span><span class="sxs-lookup"><span data-stu-id="e565d-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="e565d-289">Nie można wymusić pomiaru, ponieważ spowodowałoby to uszkodzenie stanu Quantum, który próbujemy sklonować.</span><span class="sxs-lookup"><span data-stu-id="e565d-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="e565d-290">Aby symulować operację klonowania, chcemy, aby macierz jednostkowa używała właściwości, która $$</span><span class="sxs-lookup"><span data-stu-id="e565d-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="e565d-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="e565d-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="e565d-292">dla każdego stanu $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="e565d-293">Właściwość liniowości mnożenia macierzy wskazuje, że dla każdego drugiego stanu Quantum $ \ket { \phi } $ ,</span><span class="sxs-lookup"><span data-stu-id="e565d-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="e565d-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="e565d-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="e565d-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="e565d-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="e565d-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="e565d-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="e565d-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="e565d-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="e565d-298">\right) \\\\</span></span>
    <span data-ttu-id="e565d-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="e565d-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="e565d-300">Zapewnia to podstawowe Intuition za theorem bez klonowania: każde urządzenie, które kopiuje nieznany stan Quantum, musi powodować błędy w co najmniej niektórych stanach, które kopiuje.</span><span class="sxs-lookup"><span data-stu-id="e565d-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="e565d-301">Podczas gdy klucz założono, że Cloner działa liniowo na stanie wprowadzania, może zostać naruszony poprzez dodanie i pomiar pomocniczej qubits, takie interakcje także przecieki informacji o systemie za pomocą statystyk pomiarów i zapobiegania dokładnemu klonowi w takich przypadkach.</span><span class="sxs-lookup"><span data-stu-id="e565d-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="e565d-302">Aby uzyskać bardziej szczegółowe informacje, zobacz theorem No-kloning, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="e565d-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="e565d-303">Theorema bez klonowania jest ważna w przypadku jakościowej interpretacji obliczeń opartych na usłudze Quantum, ponieważ w przypadku niedrogiego klonowania Stanów Quantum można udzielić prawie magicalej możliwości uczenia się od Stanów Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="e565d-304">Rzeczywiście można naruszyć zasadę niepewności vaunted Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="e565d-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="e565d-305">Alternatywnie można użyć optymalnej Cloner do pobrania pojedynczego przykładu ze złożonej dystrybucji Quantum i dowiedzieć się wszystkiego, co może być możliwe, aby poznać tę dystrybucję z zaledwie jednego przykładu.</span><span class="sxs-lookup"><span data-stu-id="e565d-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="e565d-306">Przypomina to Przerzucanie monet i obserwowanie głowic, a następnie na poinformowanie przyjaciela o wyniku odpowiedzi na "Ah" dystrybucja tej monety musi być Bernoulliego z $ p = 0.512643 \ ldots $ ! "</span><span class="sxs-lookup"><span data-stu-id="e565d-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="e565d-307">Taka instrukcja byłaby niesensicala, ponieważ jeden bit informacji (wynik Head) po prostu nie może udostępnić wielu bitów informacji potrzebnych do zakodowania dystrybucji bez poważnych informacji.</span><span class="sxs-lookup"><span data-stu-id="e565d-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="e565d-308">Podobnie, bez wcześniejszej informacji, nie możemy idealnie sklonować stanu Quantum, tak samo, jak nie można przygotować kompletu takich monet bez znajomości $ p $ .</span><span class="sxs-lookup"><span data-stu-id="e565d-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="e565d-309">Informacje nie są bezpłatne w obliczeniach Quantum.</span><span class="sxs-lookup"><span data-stu-id="e565d-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="e565d-310">Każda qubit mierzona w postaci pojedynczej informacji, a theorem bez klonowania nie wykazuje, że nie ma tylne wejście, które mogą być wykorzystywane w celu założenia zasadniczego kompromisu między informacjami uzyskanymi na temat systemu a zaistniałymi zakłóceniami.</span><span class="sxs-lookup"><span data-stu-id="e565d-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
