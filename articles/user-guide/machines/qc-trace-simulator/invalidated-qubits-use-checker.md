---
title: Narzędzie do sprawdzania użycia unieważnionych kubitów
description: Dowiedz się więcej na temat programu Microsoft QDK unieważniony Qubits użycia narzędzia sprawdzania poprawności, które sprawdza kod Q dla potencjalnie nieprawidłowej Qubits.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275573"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="93e5b-103">Unieważniony Qubits użycia</span><span class="sxs-lookup"><span data-stu-id="93e5b-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="93e5b-104">`Invalidated Qubits Use Checker`Jest częścią komputera Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) zaprojektowaną do wykrywania potencjalnych usterek w kodzie.</span><span class="sxs-lookup"><span data-stu-id="93e5b-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="93e5b-105">Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="93e5b-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="93e5b-106">Gdy `H` jest stosowany do `q[0]` punktów IT, do już wydanego qubit.</span><span class="sxs-lookup"><span data-stu-id="93e5b-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="93e5b-107">Może to spowodować niezdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="93e5b-107">This can cause undefined behavior.</span></span> <span data-ttu-id="93e5b-108">Gdy `Invalidated Qubits Use Checker` jest włączona, `InvalidatedQubitsUseCheckerException` zostanie zgłoszony wyjątek, jeśli operacja zostanie zastosowana do już wydanego qubit.</span><span class="sxs-lookup"><span data-stu-id="93e5b-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="93e5b-109">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="93e5b-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="93e5b-110">Używanie narzędzia sprawdzania poprawności Qubits w programie w języku C#</span><span class="sxs-lookup"><span data-stu-id="93e5b-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="93e5b-111">Poniżej znajduje się przykładowy kod sterownika języka C# do używania komputera `Trace
Simulator` z usługą Quantum z `Invalidated Qubits Use Checker` włączonymi:</span><span class="sxs-lookup"><span data-stu-id="93e5b-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="93e5b-112">Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów Quantum i może być określona jako argument dla `QCTraceSimulator` konstruktora.</span><span class="sxs-lookup"><span data-stu-id="93e5b-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="93e5b-113">Gdy `useInvalidatedQubitsUseChecker` ma wartość true, `Invalidated Qubits Use Checker` jest włączona.</span><span class="sxs-lookup"><span data-stu-id="93e5b-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="93e5b-114">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="93e5b-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="93e5b-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93e5b-115">See also</span></span> ##

- <span data-ttu-id="93e5b-116">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="93e5b-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
