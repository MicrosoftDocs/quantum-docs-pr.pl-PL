---
title: Obwody kwantowe
description: Dowiedz się, jak wizualnie reprezentować proste i złożone operacje Quantum przy użyciu diagramów obwodów Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8ba4648f1837065d15957a01ab4ca8dd2d490a42
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905152"
---
# <a name="quantum-circuits"></a><span data-ttu-id="719fc-103">Obwody Quantum</span><span class="sxs-lookup"><span data-stu-id="719fc-103">Quantum Circuits</span></span>
<span data-ttu-id="719fc-104">Rozważ chwilę przekształcenie jednostkowe $ \Text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="719fc-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="719fc-105">Ta sekwencja bram ma podstawowe znaczenie dla przetwarzania Quantum, ponieważ tworzy stan Maximally Entangled dwa qubit:</span><span class="sxs-lookup"><span data-stu-id="719fc-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="719fc-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="719fc-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="719fc-107">Operacje o tej lub większej złożoności są powszechnie stosowane w algorytmach Quantum i korekcji błędów Quantum, dlatego powinna być to świetna, że istnieje prosta metoda dla wizualizacji zwanej *diagramem obwodu Quantum*.</span><span class="sxs-lookup"><span data-stu-id="719fc-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="719fc-108">Diagram obwodu do przygotowywania tego stanu Maximally Entangled Quantum to:</span><span class="sxs-lookup"><span data-stu-id="719fc-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-109">Diagram obwodu ![dla stanu Maximally Entangled dwa qubit](~/media/Concepts1.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/Concepts1.png)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="719fc-110">Konwencje diagramu obwodu Quantum</span><span class="sxs-lookup"><span data-stu-id="719fc-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="719fc-111">Ten język wizualny dla operacji Quantum może być bardziej digestible niż zapisanie odpowiedniej macierzy po zrozumieniu Konwencji dla wyrażenia Quantum.</span><span class="sxs-lookup"><span data-stu-id="719fc-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="719fc-112">Omawiamy poniższe konwencje.</span><span class="sxs-lookup"><span data-stu-id="719fc-112">We review these conventions below.</span></span>

<span data-ttu-id="719fc-113">W diagramie obwodu każdy pełny wiersz przedstawia qubit lub bardziej ogólnie rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="719fc-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="719fc-114">Zgodnie z Konwencją Górna linia to qubit Register $0 $, a reszta jest oznaczona sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="719fc-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="719fc-115">Powyższy przykładowy obwód jest przedstawiany jako działający na dwóch qubits (lub równorzędnych dwóch rejestrach składających się z jednego qubit).</span><span class="sxs-lookup"><span data-stu-id="719fc-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="719fc-116">Bramy działające na co najmniej jednym rejestrie qubit są oznaczane jako pole.</span><span class="sxs-lookup"><span data-stu-id="719fc-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="719fc-117">Na przykład symbol</span><span class="sxs-lookup"><span data-stu-id="719fc-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-118">Symbol ![dla operacji Hadamard działającej na rejestrze z jednym qubit](~/media/concepts_2.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/concepts_2.png)</span></span>

<span data-ttu-id="719fc-119">jest operacją [Hadamard](xref:microsoft.quantum.intrinsic.h) działającą na rejestrze z jednym qubitem.</span><span class="sxs-lookup"><span data-stu-id="719fc-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="719fc-120">Bramy Quantum są uporządkowane w kolejności chronologicznej z bramą z lewej strony, jako brama po raz pierwszy zastosowana do qubits.</span><span class="sxs-lookup"><span data-stu-id="719fc-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="719fc-121">Innymi słowy, jeśli zdjęcia są nastawione jako przechowanie stanu Quantum, przewody te przesuwają stan Quantum za pośrednictwem każdej bramy na diagramie od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="719fc-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="719fc-122">To znaczy</span><span class="sxs-lookup"><span data-stu-id="719fc-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-123">![diagram bram Quantum stosuje się od lewej do prawej](~/media/concepts_3.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-123">![Diagram of quantum gates being applied left-to-right](~/media/concepts_3.png)</span></span>

<span data-ttu-id="719fc-124">jest macierzą jednostkową $CBA $.</span><span class="sxs-lookup"><span data-stu-id="719fc-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="719fc-125">Mnożenie macierzy przestrzega konwencji przeciwległej: najpierw zastosowano najbardziej odpowiednią macierz.</span><span class="sxs-lookup"><span data-stu-id="719fc-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="719fc-126">W przypadku diagramów obwodów Quantum należy najpierw zastosować bramę z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="719fc-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="719fc-127">Różnica ta może czasami prowadzić do pomyłki, dlatego ważne jest, aby zauważyć znaczącą różnicę między liniową notacją algebraicznych a diagramami obwodów Quantum.</span><span class="sxs-lookup"><span data-stu-id="719fc-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="719fc-128">Dane wejściowe i wyjściowe obwodów Quantum</span><span class="sxs-lookup"><span data-stu-id="719fc-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="719fc-129">Wszystkie poprzednie przykłady mają dokładnie taką samą liczbę przewodów (qubits) jako bramę Quantum jako liczbę przewodów z bramy Quantum.</span><span class="sxs-lookup"><span data-stu-id="719fc-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="719fc-130">Może być na początku uzasadnione, że obwody Quantum mogą mieć więcej lub mniej danych wyjściowych niż w ogóle.</span><span class="sxs-lookup"><span data-stu-id="719fc-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="719fc-131">Jest to niemożliwe, jednak ponieważ wszystkie operacje Quantum, Save pomiary, są jednostkowe i w związku z tym odwracalne.</span><span class="sxs-lookup"><span data-stu-id="719fc-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="719fc-132">Jeśli nie mają tej samej liczby danych wyjściowych, ponieważ nie byłyby one odwracalne i dlatego nie są przypadające na jednostki, co jest sprzeczne.</span><span class="sxs-lookup"><span data-stu-id="719fc-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="719fc-133">Z tego powodu każde pole rysowane na diagramie obwodu musi mieć dokładnie taką samą liczbę przewodów, jak to zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="719fc-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="719fc-134">Diagramy obwodów qubit są zgodne z podobnymi konwencjami do jednego qubit.</span><span class="sxs-lookup"><span data-stu-id="719fc-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="719fc-135">Przykładowo można zdefiniować operację jednostkową dwuqubitą, $B $ (H S\otimes X) $ i wyznaczać obwód jako</span><span class="sxs-lookup"><span data-stu-id="719fc-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-136">Diagram obwodu ![operacji jednostki dwuqubitowej](~/media/concepts_4.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-136">![Circuit diagram of a two-qubit unitary operation](~/media/concepts_4.png)</span></span>

<span data-ttu-id="719fc-137">Można również wyświetlić $B $ jako mające na celu działanie w jednym rejestrze z dwoma qubit zamiast rejestrów 2 1-qubit w zależności od kontekstu, w którym jest używany obwód.</span><span class="sxs-lookup"><span data-stu-id="719fc-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="719fc-138">Prawdopodobnie najbardziej przydatną właściwością takich diagramów obwodów abstrakcyjnych jest umożliwienie opisywania skomplikowanych algorytmów Quantum na wysokim poziomie bez konieczności kompilowania ich na podstawowe bramy.</span><span class="sxs-lookup"><span data-stu-id="719fc-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="719fc-139">Oznacza to, że można uzyskać Intuition o przepływie danych dla dużego algorytmu Quantum bez konieczności zrozumienia wszystkich szczegółowych informacji o sposobie działania poszczególnych podprocedur w algorytmie.</span><span class="sxs-lookup"><span data-stu-id="719fc-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="719fc-140">Kontrolowane bramy</span><span class="sxs-lookup"><span data-stu-id="719fc-140">Controlled gates</span></span>
<span data-ttu-id="719fc-141">Druga konstrukcja, która jest wbudowana w wieloqubit diagramy obwodu Quantum jest formantem.</span><span class="sxs-lookup"><span data-stu-id="719fc-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="719fc-142">Działanie bramki Quantum pojedynczo sterowanej, oznaczona jako $ \Lambda (G) $, gdzie wartość jednej qubit kontroluje zastosowanie $G $, można zrozumieć, przeglądając następujący przykład danych wejściowych stanu produktu $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="719fc-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="719fc-143">Oznacza to, że kontrolowana brama ma zastosowanie $G $ do rejestru zawierającego $ \psi $ if i tylko wtedy, gdy kontrolka qubit przyjmuje wartość $1 $.</span><span class="sxs-lookup"><span data-stu-id="719fc-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="719fc-144">Ogólnie rzecz biorąc, firma Microsoft opisuje takie kontrolowane operacje na diagramach obwodów jako</span><span class="sxs-lookup"><span data-stu-id="719fc-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-145">![diagram obwodu bramy z pojedynczą kontrolą](~/media/concepts_5.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-145">![Circuit diagram of a singly controlled gate](~/media/concepts_5.png)</span></span>

<span data-ttu-id="719fc-146">W tym miejscu czarne kółko oznacza bit Quantum, na którym Brama jest kontrolowana, a przewod pionowy oznacza jednostkę, która jest stosowana, gdy kontrolka qubit przyjmuje wartość $1 $.</span><span class="sxs-lookup"><span data-stu-id="719fc-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="719fc-147">W przypadku specjalnych przypadków, w których $G = X $ i $G = Z $ wprowadzamy następującą notację do opisywania kontrolowanej wersji bram (należy zauważyć, że brama sterowana X jest [bramą $CNOT $](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="719fc-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-148">![diagram obwodu dla specjalnych przypadków bram z kontrolą](~/media/concepts_6.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-148">![Circuit diagram for special cases of controlled gates](~/media/concepts_6.png)</span></span>

<span data-ttu-id="719fc-149">Polecenie Q # udostępnia metody automatycznego generowania kontrolowanej wersji operacji, która polega na tym, że programista nie ma konieczności ręcznego wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="719fc-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="719fc-150">Poniżej przedstawiono przykład:</span><span class="sxs-lookup"><span data-stu-id="719fc-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="719fc-151">Operator pomiaru</span><span class="sxs-lookup"><span data-stu-id="719fc-151">Measurement operator</span></span>
<span data-ttu-id="719fc-152">Pozostałą operacją wizualizacji na diagramach obwodu jest pomiar.</span><span class="sxs-lookup"><span data-stu-id="719fc-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="719fc-153">Miara przyjmuje rejestr qubit, mierzy go i wyprowadza wynik jako informacje klasyczne.</span><span class="sxs-lookup"><span data-stu-id="719fc-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="719fc-154">Operacja pomiaru jest określana przez symbol miernika i zawsze przyjmuje jako dane wejściowe qubit Rejestr (oznaczany przez linię ciągłą) i wyprowadza klasyczne informacje (oznaczone podwójnym wierszem).</span><span class="sxs-lookup"><span data-stu-id="719fc-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="719fc-155">W związku z tym, taki obwód jest podobny do:</span><span class="sxs-lookup"><span data-stu-id="719fc-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-156">Symbol ![reprezentujący operację pomiaru](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-156">![Symbol representing a measurement operation](~/media/concepts_7.png)</span></span>

<span data-ttu-id="719fc-157">Q # implementuje [operator miary](xref:microsoft.quantum.intrinsic.measure) do tego celu.</span><span class="sxs-lookup"><span data-stu-id="719fc-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="719fc-158">Zapoznaj się z [sekcją pomiary](xref:microsoft.quantum.libraries.standard.prelude#measurements) , aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="719fc-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="719fc-159">Analogicznie, podobwód</span><span class="sxs-lookup"><span data-stu-id="719fc-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="719fc-160">Diagram obwodu ![reprezentujący kontrolowane operacje](~/media/concepts_8.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-160">![Circuit diagram representing a controlled operation](~/media/concepts_8.png)</span></span>

<span data-ttu-id="719fc-161">zapewnia zarządzaną w trybie klasycznym bramę, w której zastosowano $G $ w warunku na klasycznej kontrolce o wartości $1 $.</span><span class="sxs-lookup"><span data-stu-id="719fc-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="719fc-162">Diagram obwodu teleportowego</span><span class="sxs-lookup"><span data-stu-id="719fc-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="719fc-163">[Teleportowanie Quantum](xref:microsoft.quantum.techniques.puttingittogether) jest prawdopodobnie najlepszym algorytmem Quantum dla zilustrowania tych składników.</span><span class="sxs-lookup"><span data-stu-id="719fc-163">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="719fc-164">Teleportowanie Quantum to metoda przenoszenia danych na komputerze z systemem Quantum (lub nawet między odległymi komputerami Quantum w sieci Quantum) za pomocą Entanglement i pomiaru.</span><span class="sxs-lookup"><span data-stu-id="719fc-164">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="719fc-165">Z tego względu można w rzeczywistości przenieść stan Quantum, wypowiedzieć wartość w danym qubit, od jednego qubit do innego, bez znajomości wartości qubit.</span><span class="sxs-lookup"><span data-stu-id="719fc-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="719fc-166">Jest to niezbędne do działania protokołu zgodnie z przepisami Mechanics Quantum.</span><span class="sxs-lookup"><span data-stu-id="719fc-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="719fc-167">Poniżej znajduje się obwód transportowy Quantum. Udostępniamy również dodaną do adnotacji wersję obwodu, która ilustruje sposób odczytywania obwodu Quantum.</span><span class="sxs-lookup"><span data-stu-id="719fc-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="719fc-168">![obwodu teleportowego Quantum](~/media/concepts_tp2.png)</span><span class="sxs-lookup"><span data-stu-id="719fc-168">![Quantum teleportation circuit](~/media/concepts_tp2.png)</span></span>
