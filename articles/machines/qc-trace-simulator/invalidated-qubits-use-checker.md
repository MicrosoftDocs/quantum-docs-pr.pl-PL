---
title: Unieważniony qubits użycia narzędzia sprawdzania poprawności | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820882"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="ad758-103">Unieważniony Qubits użycia</span><span class="sxs-lookup"><span data-stu-id="ad758-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="ad758-104">`Invalidated Qubits Use Checker` jest częścią komputera Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) zaprojektowaną do wykrywania potencjalnych usterek w kodzie.</span><span class="sxs-lookup"><span data-stu-id="ad758-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="ad758-105">Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="ad758-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="ad758-106">Gdy `H` jest stosowany do `q[0]` wskazuje już wydaną qubit.</span><span class="sxs-lookup"><span data-stu-id="ad758-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="ad758-107">Może to spowodować niezdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="ad758-107">This can cause undefined behavior.</span></span> <span data-ttu-id="ad758-108">Gdy `Invalidated Qubits Use Checker` jest włączona, wyjątek `InvalidatedQubitsUseCheckerException` zostanie wygenerowany, jeśli operacja zostanie zastosowana do już wydanego qubit.</span><span class="sxs-lookup"><span data-stu-id="ad758-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="ad758-109">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="ad758-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="ad758-110">Używanie narzędzia sprawdzania poprawności Qubits w C# programie</span><span class="sxs-lookup"><span data-stu-id="ad758-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="ad758-111">Poniżej znajduje się przykładowy kod C# sterownika służący do korzystania z komputera Quantum `Trace
Simulator` z włączonym `Invalidated Qubits Use Checker`:</span><span class="sxs-lookup"><span data-stu-id="ad758-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="ad758-112">Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów z Quantum i może być określona jako argument dla konstruktora `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="ad758-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="ad758-113">Gdy `useInvalidatedQubitsUseChecker` ma wartość true, `Invalidated Qubits Use Checker` jest włączona.</span><span class="sxs-lookup"><span data-stu-id="ad758-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="ad758-114">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ad758-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad758-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ad758-115">See also</span></span> ##

- <span data-ttu-id="ad758-116">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="ad758-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
