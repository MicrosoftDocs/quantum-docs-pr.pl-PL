---
title: Symulator śledzenia komputera kwantowego | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820440"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="b1815-103">Symulator śledzenia kwantowego</span><span class="sxs-lookup"><span data-stu-id="b1815-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="b1815-104">Symulator śledzenia komputera kwantowego firmy Microsoft umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b1815-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="b1815-105">Pozwala to symulatorowi śledzenia wykonywać programy kwantowe korzystające z tysięcy kubitów.</span><span class="sxs-lookup"><span data-stu-id="b1815-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="b1815-106">Wyróżniamy dwa główne zastosowania takiego symulatora:</span><span class="sxs-lookup"><span data-stu-id="b1815-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="b1815-107">Debugowanie kodu klasycznego, który jest częścią programu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b1815-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="b1815-108">Szacowanie zasobów wymaganych do uruchomienia danego wystąpienia programu kwantowego na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="b1815-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="b1815-109">W przypadku konieczności wykonywania pomiarów symulator śledzenia korzysta z dodatkowych informacji podawanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b1815-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="b1815-110">Aby uzyskać więcej informacji na ten temat, zobacz sekcję [Podawanie prawdopodobieństwa wyników pomiarów](#providing-the-probability-of-measurement-outcomes).</span><span class="sxs-lookup"><span data-stu-id="b1815-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b1815-111">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="b1815-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="b1815-112">W algorytmach kwantowych są używane dwa rodzaje pomiarów.</span><span class="sxs-lookup"><span data-stu-id="b1815-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="b1815-113">Pierwszy odgrywa rolę pomocniczą — użytkownik zazwyczaj zna prawdopodobieństwo wystąpienia wyników.</span><span class="sxs-lookup"><span data-stu-id="b1815-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="b1815-114">W takim przypadku użytkownik może napisać operację <xref:microsoft.quantum.intrinsic.assertprob> w przestrzeni nazw <xref:microsoft.quantum.intrinsic>, aby udostępnić te informacje.</span><span class="sxs-lookup"><span data-stu-id="b1815-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="b1815-115">Zostało to przedstawione w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="b1815-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="b1815-116">Gdy symulator śledzenia wykona operację `AssertProb`, zarejestruje wynik `Zero` dla wartości `PauliZ` w elementach `source` i `q` z prawdopodobieństwem 0,5.</span><span class="sxs-lookup"><span data-stu-id="b1815-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="b1815-117">Gdy symulator wykona później operację `M`, znajdzie zarejestrowane wartości prawdopodobieństwa wyników, a operacja `M` zwróci element `Zero` lub `One` z prawdopodobieństwem 0,5.</span><span class="sxs-lookup"><span data-stu-id="b1815-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="b1815-118">Jeśli ten sam kod zostanie wykonany w symulatorze, który śledzi stan kwantowy, symulator sprawdzi, czy prawdopodobieństwa podane w operacji `AssertProb` są poprawne.</span><span class="sxs-lookup"><span data-stu-id="b1815-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="b1815-119">Uruchamianie programu za pomocą symulatora śledzenia komputera kwantowego</span><span class="sxs-lookup"><span data-stu-id="b1815-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="b1815-120">Symulator śledzenia komputera kwantowego można traktować jako zwykłą maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="b1815-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="b1815-121">Program sterujący w języku C# umożliwiający korzystania z symulatora jest bardzo podobny do programu dla dowolnego innego symulatora kwantowego:</span><span class="sxs-lookup"><span data-stu-id="b1815-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="b1815-122">Należy pamiętać, że jeśli istnieje co najmniej jeden pomiar nieopisany przy użyciu operacji `AssertProb`, symulator zgłosi wyjątek `UnconstrainedMeasurementException` w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="b1815-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="b1815-123">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API dotyczącą wyjątku [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).</span><span class="sxs-lookup"><span data-stu-id="b1815-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="b1815-124">Symulator śledzenia nie tylko pozwala uruchamiać programy kwantowe. Zawiera on pięć składników, które umożliwiają wykrywanie usterek w programach i wykonywanie oszacowań zasobów programu kwantowego:</span><span class="sxs-lookup"><span data-stu-id="b1815-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="b1815-125">Narzędzie do sprawdzania odrębnych danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="b1815-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="b1815-126">Narzędzie do sprawdzania użycia nieprawidłowych kubitów</span><span class="sxs-lookup"><span data-stu-id="b1815-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="b1815-127">Licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="b1815-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="b1815-128">Licznik głębokości obwodu</span><span class="sxs-lookup"><span data-stu-id="b1815-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="b1815-129">Licznik szerokości obwodu</span><span class="sxs-lookup"><span data-stu-id="b1815-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="b1815-130">Poszczególne składniki włącza się, ustawiając odpowiednie flagi w klasie `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="b1815-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="b1815-131">Więcej informacji o używaniu tych składników można znaleźć w odpowiednich plikach dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="b1815-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="b1815-132">Aby uzyskać szczegółowe informacje, zobacz dokumentację interfejsu API dotyczącą klasy [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b1815-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1815-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1815-133">See also</span></span>
<span data-ttu-id="b1815-134">Dokumentacja [symulatora śledzenia](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) komputera kwantowego dla języka C#</span><span class="sxs-lookup"><span data-stu-id="b1815-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

