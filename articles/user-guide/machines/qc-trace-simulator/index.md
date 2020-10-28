---
title: Symulator śledzenia kwantowego — zestaw Quantum Development Kit
description: Dowiedz się, jak za pomocą symulatora śledzenia komputera kwantowego firmy Microsoft debugować klasyczny kod i szacować wymagania dotyczące zasobów programu w języku :::no-loc(Q#):::.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 2e2d9f8494d8709fba34123793cecce4011b609a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690831"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="1c5f0-103">Symulator śledzenia kwantowego zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="1c5f0-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="1c5f0-104">Klasa <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> zestawu QDK uruchamia program kwantowy bez faktycznego symulowania stanu komputera kwantowego.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="1c5f0-105">Pozwala to symulatorowi śledzenia kwantowego wykonywać programy kwantowe korzystające z tysięcy kubitów.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="1c5f0-106">Wyróżniamy dwa główne zastosowania takiego symulatora:</span><span class="sxs-lookup"><span data-stu-id="1c5f0-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="1c5f0-107">Debugowanie kodu klasycznego, który jest częścią programu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="1c5f0-108">Szacowanie zasobów wymaganych do uruchomienia danego wystąpienia programu kwantowego na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="1c5f0-109">W rzeczywistości [narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator) zapewniające bardziej ograniczony zestaw metryk jest oparte na symulatorze śledzenia.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="1c5f0-110">Wywoływanie symulatora śledzenia kwantowego</span><span class="sxs-lookup"><span data-stu-id="1c5f0-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="1c5f0-111">Za pomocą symulatora śledzenia kwantowego można uruchomić dowolną operację w języku :::no-loc(Q#):::.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-111">You can use the quantum trace simulator to run any :::no-loc(Q#)::: operation.</span></span>

<span data-ttu-id="1c5f0-112">Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `QCTraceSimulator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="1c5f0-113">Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `QCTraceSimulator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="1c5f0-114">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="1c5f0-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="1c5f0-115">Ponieważ symulator śledzenia kwantowego nie symuluje rzeczywistego stanu kwantowego, nie może on obliczyć prawdopodobieństwa wyników pomiaru w ramach operacji.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="1c5f0-116">W związku z tym jeśli operacja obejmuje pomiary, należy jawnie podać te prawdopodobieństwa przy użyciu operacji <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z przestrzeni nazw <xref:Microsoft.Quantum.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation from the <xref:Microsoft.Quantum.Diagnostics> namespace.</span></span> <span data-ttu-id="1c5f0-117">Zostało to przedstawione w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="1c5f0-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="1c5f0-118">Gdy symulator śledzenia kwantowego napotka element `AssertMeasurementProbability`, zarejestruje wynik `Zero` dla wartości `PauliZ` w elementach `source` i `q` z prawdopodobieństwem **0.5** .</span><span class="sxs-lookup"><span data-stu-id="1c5f0-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5** .</span></span> <span data-ttu-id="1c5f0-119">Po uruchomieniu później operacji `M` symulator odnajdzie zarejestrowane wartości prawdopodobieństwa wyniku, a operacja `M` zwróci wartość `Zero` lub `One` z prawdopodobieństwem **0.5** .</span><span class="sxs-lookup"><span data-stu-id="1c5f0-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5** .</span></span> <span data-ttu-id="1c5f0-120">Jeśli ten sam kod zostanie wykonany w symulatorze, który śledzi stan kwantowy, taki symulator sprawdzi, czy prawdopodobieństwa podane w operacji `AssertMeasurementProbability` są poprawne.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="1c5f0-121">Należy pamiętać, że jeśli istnieje co najmniej jedna operacja pomiaru nieopisana przy użyciu elementu `AssertMeasurementProbability`, symulator zgłosi wyjątek [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="1c5f0-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="1c5f0-122">Narzędzia symulatora śledzenia kwantowego</span><span class="sxs-lookup"><span data-stu-id="1c5f0-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="1c5f0-123">Zestaw QDK obejmuje pięć narzędzi, których można używać z symulatorem śledzenia kwantowego do wykrywania usterek w programach i wykonywania szacowania zasobów programu kwantowego:</span><span class="sxs-lookup"><span data-stu-id="1c5f0-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="1c5f0-124">Narzędzie</span><span class="sxs-lookup"><span data-stu-id="1c5f0-124">Tool</span></span> | <span data-ttu-id="1c5f0-125">Opis</span><span class="sxs-lookup"><span data-stu-id="1c5f0-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="1c5f0-126">Narzędzie do sprawdzania odrębnych danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="1c5f0-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="1c5f0-127">Sprawdza potencjalne konflikty z współdzielonymi kubitami</span><span class="sxs-lookup"><span data-stu-id="1c5f0-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="1c5f0-128">Narzędzie do sprawdzania użycia unieważnionych kubitów</span><span class="sxs-lookup"><span data-stu-id="1c5f0-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="1c5f0-129">Sprawdza, czy program stosuje operację względem kubitu, który został już zwolniony</span><span class="sxs-lookup"><span data-stu-id="1c5f0-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="1c5f0-130">Licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="1c5f0-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="1c5f0-131">Zlicza liczbę procesów pierwotnych używanych przez każdą operację wywoływaną w programie kwantowym</span><span class="sxs-lookup"><span data-stu-id="1c5f0-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="1c5f0-132">Licznik głębokości</span><span class="sxs-lookup"><span data-stu-id="1c5f0-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="1c5f0-133">Zbiera liczniki reprezentujące dolną granicę głębokości każdej operacji wywołanej w programie kwantowym</span><span class="sxs-lookup"><span data-stu-id="1c5f0-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="1c5f0-134">Licznik szerokości</span><span class="sxs-lookup"><span data-stu-id="1c5f0-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="1c5f0-135">Zlicza liczbę kubitów przydzieloną i zapożyczoną przez każdą operację w programie kwantowym</span><span class="sxs-lookup"><span data-stu-id="1c5f0-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="1c5f0-136">Każde z tych narzędzi jest włączane przez ustawienie odpowiednich flag w konfiguracji `QCTraceSimulatorConfiguration`, a następnie przekazanie konfiguracji do deklaracji programu `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="1c5f0-137">Aby uzyskać informacje na temat korzystania z każdego z tych narzędzi, zobacz linki na powyższej liście.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="1c5f0-138">Aby uzyskać więcej informacji na temat konfigurowania programu `QCTraceSimulator`, zobacz [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1c5f0-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="1c5f0-139">Metody programu QCTraceSimulator</span><span class="sxs-lookup"><span data-stu-id="1c5f0-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="1c5f0-140">Program `QCTraceSimulator` ma kilka wbudowanych metod służących do pobierania wartości metryk śledzonych podczas operacji kwantowej.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="1c5f0-141">Przykłady metod [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) i [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) można znaleźć w artykułach [Licznik operacji pierwotnych](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Licznik głębokości](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) i [Licznik szerokości](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="1c5f0-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="1c5f0-142">Aby uzyskać więcej informacji na temat wszystkich dostępnych metod, zobacz [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) w dokumentacji interfejsu API języka :::no-loc(Q#):::.</span><span class="sxs-lookup"><span data-stu-id="1c5f0-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the :::no-loc(Q#)::: API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1c5f0-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1c5f0-143">See also</span></span>

- [<span data-ttu-id="1c5f0-144">Narzędzie do szacowania zasobów kwantowych</span><span class="sxs-lookup"><span data-stu-id="1c5f0-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="1c5f0-145">Kwantowy symulator Toffoli</span><span class="sxs-lookup"><span data-stu-id="1c5f0-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="1c5f0-146">Kwantowy symulator pełnego stanu</span><span class="sxs-lookup"><span data-stu-id="1c5f0-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 