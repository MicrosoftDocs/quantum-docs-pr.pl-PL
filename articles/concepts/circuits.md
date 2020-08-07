---
<span data-ttu-id="b5cf5-101">title: Opis obwodów Quantum: informacje o wizualizacji reprezentują proste i złożone operacje Quantum przy użyciu diagramów obwodów Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="b5cf5-102">Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Circuits MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:</span><span class="sxs-lookup"><span data-stu-id="b5cf5-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="b5cf5-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-103">"Q#"</span></span>
- <span data-ttu-id="b5cf5-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-104">"$$v"</span></span>
- <span data-ttu-id="b5cf5-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-105">"$$"</span></span>
- <span data-ttu-id="b5cf5-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-106">"$$"</span></span>
- <span data-ttu-id="b5cf5-107">"$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-107">"$"</span></span>
- <span data-ttu-id="b5cf5-108">"$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-108">"$"</span></span>
- <span data-ttu-id="b5cf5-109">"$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-109">"$"</span></span>
- <span data-ttu-id="b5cf5-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-110">"$$"</span></span>
- <span data-ttu-id="b5cf5-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-111">"\cdots"</span></span>
- <span data-ttu-id="b5cf5-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-112">"bmatrix"</span></span>
- <span data-ttu-id="b5cf5-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-113">"\ddots"</span></span>
- <span data-ttu-id="b5cf5-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-114">"\equiv"</span></span>
- <span data-ttu-id="b5cf5-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-115">"\sum"</span></span>
- <span data-ttu-id="b5cf5-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-116">"\begin"</span></span>
- <span data-ttu-id="b5cf5-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-117">"\end"</span></span>
- <span data-ttu-id="b5cf5-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-118">"\sqrt"</span></span>
- <span data-ttu-id="b5cf5-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-119">"\otimes"</span></span>
- <span data-ttu-id="b5cf5-120">"{"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-120">"{"</span></span>
- <span data-ttu-id="b5cf5-121">"}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-121">"}"</span></span>
- <span data-ttu-id="b5cf5-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-122">"\text"</span></span>
- <span data-ttu-id="b5cf5-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-123">"\phi"</span></span>
- <span data-ttu-id="b5cf5-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-124">"\kappa"</span></span>
- <span data-ttu-id="b5cf5-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-125">"\psi"</span></span>
- <span data-ttu-id="b5cf5-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-126">"\alpha"</span></span>
- <span data-ttu-id="b5cf5-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-127">"\beta"</span></span>
- <span data-ttu-id="b5cf5-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-128">"\gamma"</span></span>
- <span data-ttu-id="b5cf5-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-129">"\delta"</span></span>
- <span data-ttu-id="b5cf5-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-130">"\omega"</span></span>
- <span data-ttu-id="b5cf5-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-131">"\bra"</span></span>
- <span data-ttu-id="b5cf5-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-132">"\ket"</span></span>
- <span data-ttu-id="b5cf5-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-133">"\boldone"</span></span>
- <span data-ttu-id="b5cf5-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-134">"\\\\"</span></span>
- <span data-ttu-id="b5cf5-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-135">"\\"</span></span>
- <span data-ttu-id="b5cf5-136">"="</span><span class="sxs-lookup"><span data-stu-id="b5cf5-136">"="</span></span>
- <span data-ttu-id="b5cf5-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-137">"\frac"</span></span>
- <span data-ttu-id="b5cf5-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-138">"\text"</span></span>
- <span data-ttu-id="b5cf5-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-139">"\mapsto"</span></span>
- <span data-ttu-id="b5cf5-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-140">"\dagger"</span></span>
- <span data-ttu-id="b5cf5-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-141">"\to"</span></span>
- <span data-ttu-id="b5cf5-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-142">"\begin{cases}"</span></span>
- <span data-ttu-id="b5cf5-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-143">"\end{cases}"</span></span>
- <span data-ttu-id="b5cf5-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-144">"\operatorname"</span></span>
- <span data-ttu-id="b5cf5-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-145">"\braket"</span></span>
- <span data-ttu-id="b5cf5-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-146">"\id"</span></span>
- <span data-ttu-id="b5cf5-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-147">"\expect"</span></span>
- <span data-ttu-id="b5cf5-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-148">"\defeq"</span></span>
- <span data-ttu-id="b5cf5-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-149">"\variance"</span></span>
- <span data-ttu-id="b5cf5-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-150">"\dd"</span></span>
- <span data-ttu-id="b5cf5-151">"&"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-151">"&"</span></span>
- <span data-ttu-id="b5cf5-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-152">"\begin{align}"</span></span>
- <span data-ttu-id="b5cf5-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-153">"\end{align}"</span></span>
- <span data-ttu-id="b5cf5-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-154">"\Lambda"</span></span>
- <span data-ttu-id="b5cf5-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-155">"\lambda"</span></span>
- <span data-ttu-id="b5cf5-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-156">"\Omega"</span></span>
- <span data-ttu-id="b5cf5-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-157">"\mathrm"</span></span>
- <span data-ttu-id="b5cf5-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-158">"\left"</span></span>
- <span data-ttu-id="b5cf5-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-159">"\right"</span></span>
- <span data-ttu-id="b5cf5-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-160">"\qquad"</span></span>
- <span data-ttu-id="b5cf5-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-161">"\times"</span></span>
- <span data-ttu-id="b5cf5-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-162">"\big"</span></span>
- <span data-ttu-id="b5cf5-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-163">"\langle"</span></span>
- <span data-ttu-id="b5cf5-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-164">"\rangle"</span></span>
- <span data-ttu-id="b5cf5-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-165">"\bigg"</span></span>
- <span data-ttu-id="b5cf5-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-166">"\Big"</span></span>
- <span data-ttu-id="b5cf5-167">"|"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-167">"|"</span></span>
- <span data-ttu-id="b5cf5-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-168">"\mathbb"</span></span>
- <span data-ttu-id="b5cf5-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-169">"\vec"</span></span>
- <span data-ttu-id="b5cf5-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-170">"\in"</span></span>
- <span data-ttu-id="b5cf5-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-171">"\texttt"</span></span>
- <span data-ttu-id="b5cf5-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-172">"\ne"</span></span>
- <span data-ttu-id="b5cf5-173">"<"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-173">"<"</span></span>
- <span data-ttu-id="b5cf5-174">">"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-174">">"</span></span>
- <span data-ttu-id="b5cf5-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-175">"\leq"</span></span>
- <span data-ttu-id="b5cf5-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-176">"\geq"</span></span>
- <span data-ttu-id="b5cf5-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-177">"~~"</span></span>
- <span data-ttu-id="b5cf5-178">"~"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-178">"~"</span></span>
- <span data-ttu-id="b5cf5-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="b5cf5-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="b5cf5-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="b5cf5-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="b5cf5-182">Obwody Quantum</span><span class="sxs-lookup"><span data-stu-id="b5cf5-182">Quantum Circuits</span></span>
<span data-ttu-id="b5cf5-183">Rozważ chwilę przekształcenie jednostkowe $ \text { CNOT } _ { 01 } (H \otimes 1) $ .</span><span class="sxs-lookup"><span data-stu-id="b5cf5-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="b5cf5-184">Ta sekwencja bram ma podstawowe znaczenie dla przetwarzania Quantum, ponieważ tworzy stan Maximally Entangled dwa qubit:</span><span class="sxs-lookup"><span data-stu-id="b5cf5-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="b5cf5-185">$$\mathrm{CNOT } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$</span><span class="sxs-lookup"><span data-stu-id="b5cf5-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="b5cf5-186">Operacje o tej lub większej złożoności są powszechnie stosowane w algorytmach Quantum i korekcji błędów Quantum, dlatego powinna być to świetna, że istnieje prosta metoda dla wizualizacji zwanej *diagramem obwodu Quantum*.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="b5cf5-187">Diagram obwodu do przygotowywania tego stanu Maximally Entangled Quantum to:</span><span class="sxs-lookup"><span data-stu-id="b5cf5-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="b5cf5-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="b5cf5-189"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-190">![Diagram obwodu dla stanu Maximally Entangled dwa qubit](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="b5cf5-191">Konwencje diagramu obwodu Quantum</span><span class="sxs-lookup"><span data-stu-id="b5cf5-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="b5cf5-192">Ten język wizualny dla operacji Quantum może być bardziej digestible niż zapisanie odpowiedniej macierzy po zrozumieniu Konwencji dla wyrażenia Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="b5cf5-193">Omawiamy poniższe konwencje.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-193">We review these conventions below.</span></span>

<span data-ttu-id="b5cf5-194">W diagramie obwodu każdy pełny wiersz przedstawia qubit lub bardziej ogólnie rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="b5cf5-195">Zgodnie z Konwencją Górna linia to qubit Register $ 0 $ , a reszta jest oznaczona sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="b5cf5-196">Powyższy przykładowy obwód jest przedstawiany jako działający na dwóch qubits (lub równorzędnych dwóch rejestrach składających się z jednego qubit).</span><span class="sxs-lookup"><span data-stu-id="b5cf5-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="b5cf5-197">Bramy działające na co najmniej jednym rejestrie qubit są oznaczane jako pole.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="b5cf5-198">Na przykład symbol</span><span class="sxs-lookup"><span data-stu-id="b5cf5-198">For example, the symbol</span></span>

<span data-ttu-id="b5cf5-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="b5cf5-200"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-201">![Symbol operacji Hadamard działającej w rejestrze jednoqubitnym](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="b5cf5-202">jest operacją [Hadamard](xref:microsoft.quantum.intrinsic.h) działającą na rejestrze z jednym qubitem.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-202">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="b5cf5-203">Bramy Quantum są uporządkowane w kolejności chronologicznej z bramą z lewej strony, jako brama po raz pierwszy zastosowana do qubits.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="b5cf5-204">Innymi słowy, jeśli zdjęcia są nastawione jako przechowanie stanu Quantum, przewody te przesuwają stan Quantum za pośrednictwem każdej bramy na diagramie od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="b5cf5-205">To znaczy</span><span class="sxs-lookup"><span data-stu-id="b5cf5-205">That is to say</span></span> 

<span data-ttu-id="b5cf5-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="b5cf5-207"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-208">![Diagram bram Quantum jest stosowany od lewej do prawej](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="b5cf5-209">jest obsługiwanie macierzy jednostkowej $ $ .</span><span class="sxs-lookup"><span data-stu-id="b5cf5-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="b5cf5-210">Mnożenie macierzy przestrzega konwencji przeciwległej: najpierw zastosowano najbardziej odpowiednią macierz.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="b5cf5-211">W przypadku diagramów obwodów Quantum należy najpierw zastosować bramę z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="b5cf5-212">Różnica ta może czasami prowadzić do pomyłki, dlatego ważne jest, aby zauważyć znaczącą różnicę między liniową notacją algebraicznych a diagramami obwodów Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="b5cf5-213">Dane wejściowe i wyjściowe obwodów Quantum</span><span class="sxs-lookup"><span data-stu-id="b5cf5-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="b5cf5-214">Wszystkie poprzednie przykłady mają dokładnie taką samą liczbę przewodów (qubits) jako bramę Quantum jako liczbę przewodów z bramy Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="b5cf5-215">Może być na początku uzasadnione, że obwody Quantum mogą mieć więcej lub mniej danych wyjściowych niż w ogóle.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="b5cf5-216">Jest to niemożliwe, jednak ponieważ wszystkie operacje Quantum, Save pomiary, są jednostkowe i w związku z tym odwracalne.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="b5cf5-217">Jeśli nie mają tej samej liczby danych wyjściowych, ponieważ nie byłyby one odwracalne i dlatego nie są przypadające na jednostki, co jest sprzeczne.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="b5cf5-218">Z tego powodu każde pole rysowane na diagramie obwodu musi mieć dokładnie taką samą liczbę przewodów, jak to zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="b5cf5-219">Diagramy obwodów qubit są zgodne z podobnymi konwencjami do jednego qubit.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="b5cf5-220">Przykładowo można zdefiniować qubit operacji jednostkowej $ B jako $ $ (H S \otimes X) i wystawić $ obwód jako</span><span class="sxs-lookup"><span data-stu-id="b5cf5-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="b5cf5-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="b5cf5-222"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-223">![Diagram obwodu operacji jednostki dwuqubitowej](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="b5cf5-224">Można również wyświetlić $ B $ jako akcję w jednym rejestrze z dwoma qubit 2 1 zamiast rejestrów qubit, w zależności od kontekstu, w którym jest używany obwód.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="b5cf5-225">Prawdopodobnie najbardziej przydatną właściwością takich diagramów obwodów abstrakcyjnych jest umożliwienie opisywania skomplikowanych algorytmów Quantum na wysokim poziomie bez konieczności kompilowania ich na podstawowe bramy.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="b5cf5-226">Oznacza to, że można uzyskać Intuition o przepływie danych dla dużego algorytmu Quantum bez konieczności zrozumienia wszystkich szczegółowych informacji o sposobie działania poszczególnych podprocedur w algorytmie.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="b5cf5-227">Kontrolowane bramy</span><span class="sxs-lookup"><span data-stu-id="b5cf5-227">Controlled gates</span></span>
<span data-ttu-id="b5cf5-228">Druga konstrukcja, która jest wbudowana w wieloqubit diagramy obwodu Quantum jest formantem.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="b5cf5-229">Działanie bramki "Quantum" z pojedynczą kontrolą $ \Lambda (G) $ , gdzie wartość jednego qubit steruje zastosowaniem $ G $ , można zrozumieć, przeglądając następujący przykład danych wejściowych stanu produktu $ \Lambda (g) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ . Oznacza to, że kontrolowana Brama stosuje $ G $ do rejestru zawierającego $ \psi $ if i tylko wtedy, gdy kontrolka qubit Pobiera wartość $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b5cf5-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="b5cf5-230">Ogólnie rzecz biorąc, firma Microsoft opisuje takie kontrolowane operacje na diagramach obwodów jako</span><span class="sxs-lookup"><span data-stu-id="b5cf5-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="b5cf5-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="b5cf5-232"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-233">![Diagram obwodu bramy z pojedynczą kontrolą](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="b5cf5-234">W tym miejscu czarne kółko oznacza bit Quantum, dla którego Brama jest kontrolowana, a przewod pionowy oznacza jednostkę, która jest stosowana, gdy kontrolka qubit Pobiera wartość $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b5cf5-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="b5cf5-235">W przypadku specjalnych przypadków, w których $ G = X $ i $ g. = $ wprowadzamy następującą notację do opisywania kontrolowanej wersji bram (należy zauważyć, że brama sterowana X jest [ $ $ bramą CNOT](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="b5cf5-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<span data-ttu-id="b5cf5-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="b5cf5-237"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-238">![Diagram obwodu dla specjalnych przypadków sterowanych bram](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="b5cf5-239">Q#zapewnia metody automatycznego generowania kontrolowanej wersji operacji, która polega na tym, że programista nie ma konieczności ręcznego wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="b5cf5-240">Poniżej przedstawiono przykład:</span><span class="sxs-lookup"><span data-stu-id="b5cf5-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="b5cf5-241">Operator pomiaru</span><span class="sxs-lookup"><span data-stu-id="b5cf5-241">Measurement operator</span></span>
<span data-ttu-id="b5cf5-242">Pozostałą operacją wizualizacji na diagramach obwodu jest pomiar.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="b5cf5-243">Miara przyjmuje rejestr qubit, mierzy go i wyprowadza wynik jako informacje klasyczne.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="b5cf5-244">Operacja pomiaru jest określana przez symbol miernika i zawsze przyjmuje jako dane wejściowe qubit Rejestr (oznaczany przez linię ciągłą) i wyprowadza klasyczne informacje (oznaczone podwójnym wierszem).</span><span class="sxs-lookup"><span data-stu-id="b5cf5-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="b5cf5-245">W związku z tym, taki obwód jest podobny do:</span><span class="sxs-lookup"><span data-stu-id="b5cf5-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="b5cf5-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="b5cf5-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="b5cf5-247"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-248">![Symbol reprezentujący operację pomiaru](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="b5cf5-249">Q#implementuje [operator miary](xref:microsoft.quantum.intrinsic.measure) do tego celu.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-249">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="b5cf5-250">Zapoznaj się z [sekcją pomiary](xref:microsoft.quantum.libraries.standard.prelude#measurements) , aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="b5cf5-251">Analogicznie, podobwód</span><span class="sxs-lookup"><span data-stu-id="b5cf5-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="b5cf5-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="b5cf5-253"><!--Nie może znaleźć możliwości łatwego wyśrodkowania tego elementu... prawdopodobnie wymagana jest rozszerzenie:--></span><span class="sxs-lookup"><span data-stu-id="b5cf5-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="b5cf5-254">![Diagram obwodu reprezentujący operację kontrolowana](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="b5cf5-255">zapewnia bramie sterowanej klasycznym, gdzie $ G $ jest zastosowany w przypadku, gdy jest to wartość $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b5cf5-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="b5cf5-256">Diagram obwodu teleportowego</span><span class="sxs-lookup"><span data-stu-id="b5cf5-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="b5cf5-257">Teleportowanie Quantum jest prawdopodobnie najlepszym algorytmem Quantum dla zilustrowania tych składników.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="b5cf5-258">Możesz poznać praktyczne użycie odpowiedniej teleport Quantum [Kata](xref:microsoft.quantum.overview.katas) Quantum, jest metodą przenoszenia danych na komputerze z systemem Quantum (lub nawet między odległymi komputerami Quantum w sieci Quantum) za pomocą Entanglement i pomiaru.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="b5cf5-259">Z tego względu można w rzeczywistości przenieść stan Quantum, wypowiedzieć wartość w danym qubit, od jednego qubit do innego, bez znajomości wartości qubit.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="b5cf5-260">Jest to niezbędne do działania protokołu zgodnie z przepisami Mechanics Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="b5cf5-261">Poniżej znajduje się obwód transportowy Quantum. Udostępniamy również dodaną do adnotacji wersję obwodu, która ilustruje sposób odczytywania obwodu Quantum.</span><span class="sxs-lookup"><span data-stu-id="b5cf5-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="b5cf5-262"><!--- ![](.\media\tp2.svg) { Szerokość = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="b5cf5-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="b5cf5-263">![Obwód teleportowy Quantum](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="b5cf5-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
