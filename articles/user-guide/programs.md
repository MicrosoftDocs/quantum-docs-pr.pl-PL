---
title: 'Q # Introdution'
description: 'Szybkie wprowadzenie do programów Quantum w usłudze Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233975"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="f9f62-103">Język programowania Q # Quantum</span><span class="sxs-lookup"><span data-stu-id="f9f62-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="f9f62-104">Wszystko, co musisz wiedzieć o języku programowania Q #, opisano szczegółowo w [przewodniku językowym q #](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="f9f62-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="f9f62-105">Podobnie jak w przypadku innych, nasz [proces projektowania języka](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) jest typu open source i Zapraszamy do powitania.</span><span class="sxs-lookup"><span data-stu-id="f9f62-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="f9f62-106">Aby uzyskać więcej informacji o wykrytych i motywacji za Q #, zobacz [Dlaczego potrzebuję q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="f9f62-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="f9f62-107">Polecenie Q # jest dostarczane jako część zestawu Quantum Development Kit (QDK), aby zapoznać się z szybkim omówieniem, Dowiedz [się, co to jest QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="f9f62-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="f9f62-108">Co to jest program Quantum?</span><span class="sxs-lookup"><span data-stu-id="f9f62-108">What is a quantum program?</span></span>

<span data-ttu-id="f9f62-109">Program Quantum może być traktowany jako konkretny zestaw klasycznych podprocedur, które, po wywołaniu, wykonują obliczenia poprzez współdziałanie z systemem Quantum; Program pisany w języku Q # nie bezpośrednio modeluje stan Quantum, ale raczej opisuje, jak klasyczny formant współdziała z qubits.</span><span class="sxs-lookup"><span data-stu-id="f9f62-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="f9f62-110">Pozwala to na całkowite niezależny od informacji o stanie *Quantum nawet na* każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny.</span><span class="sxs-lookup"><span data-stu-id="f9f62-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="f9f62-111">Ważną konsekwencją jest to, że funkcja Q # nie ma możliwości Introspect do stanu qubit lub innych właściwości Quantum Mechanics bezpośrednio, co gwarantuje, że program Q # może być fizycznie wykonywany na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9f62-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="f9f62-112">Zamiast tego program może wywołać operacje, takie jak [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) Wyodrębnienie informacji klasycznych z qubit.</span><span class="sxs-lookup"><span data-stu-id="f9f62-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="f9f62-113">Po przydzieleniu qubit może być przekazane do operacji i funkcji *, nazywanych również jako możliwe* do wypróbowania.</span><span class="sxs-lookup"><span data-stu-id="f9f62-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="f9f62-114">W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit; Wszystkie bezpośrednie działania w stanie qubit są wszystkie zdefiniowane przez *wewnętrzne* , takie jak [`X`](xref:Microsoft.Quantum.Intrinsic.X) i [`H`](xref:Microsoft.Quantum.Intrinsic.H) -tj., których implementacje nie są zdefiniowane w Q #, ale są definiowane przez maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="f9f62-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="f9f62-115">Operacje, *które faktycznie są* wykonywane, są tworzone wyłącznie przez maszynę docelową używaną do uruchamiania określonego programu Q #.</span><span class="sxs-lookup"><span data-stu-id="f9f62-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="f9f62-116">Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykonuje odpowiednie operacje matematyczne w symulowanym systemie Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9f62-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="f9f62-117">Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji w Q # spowoduje skierowanie komputera Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum (np. precyzyjne impulsy laserowe).</span><span class="sxs-lookup"><span data-stu-id="f9f62-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="f9f62-118">Program Q # ponownie łączy te operacje jako zdefiniowane przez maszynę docelową w celu utworzenia nowych, wyższych operacji na potrzeby obliczeń Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9f62-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="f9f62-119">W ten sposób Q # ułatwia wyrażanie logiki podstawowych algorytmów Quantum i hybrydowych procesów Quantum — klasycznych, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.</span><span class="sxs-lookup"><span data-stu-id="f9f62-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="f9f62-120">Prostym przykładem jest następujący program, który przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="f9f62-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="f9f62-121">Nasze [Katas Quantum](https://github.com/microsoft/QuantumKatas#introduction) zapewniają dobre wprowadzenie w oparciu o [koncepcje przetwarzania Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , takie jak typowe operacje Quantum i sposób manipulowania qubits.</span><span class="sxs-lookup"><span data-stu-id="f9f62-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="f9f62-122">Więcej przykładów można znaleźć w temacie [operacje wewnętrzne i funkcje](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="f9f62-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



