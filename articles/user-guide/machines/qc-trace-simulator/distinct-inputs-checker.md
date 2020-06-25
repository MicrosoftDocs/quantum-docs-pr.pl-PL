---
title: Sprawdzanie odrębnych wejść
description: Dowiedz się więcej na temat narzędzia sprawdzania danych wejściowych programu Microsoft QDK, które sprawdza kod Q, aby uzyskać potencjalne konflikty z współdzielonym qubits.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275621"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="742ca-103">Sprawdzanie odrębnych wejść</span><span class="sxs-lookup"><span data-stu-id="742ca-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="742ca-104">`Distinct Inputs Checker`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="742ca-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="742ca-105">Jest ona przeznaczona do wykrywania potencjalnych usterek w kodzie.</span><span class="sxs-lookup"><span data-stu-id="742ca-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="742ca-106">Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez ten pakiet:</span><span class="sxs-lookup"><span data-stu-id="742ca-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="742ca-107">Gdy użytkownik przegląda ten program, zakłada, że kolejność, w której `op1` `op2` są wywoływane, nie ma znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch.</span><span class="sxs-lookup"><span data-stu-id="742ca-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="742ca-108">Teraz Rozważmy przykład, w którym ta operacja jest używana:</span><span class="sxs-lookup"><span data-stu-id="742ca-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="742ca-109">Teraz `op1` i `op2` są one uzyskiwane przy użyciu częściowej aplikacji i udostępniają qubit.</span><span class="sxs-lookup"><span data-stu-id="742ca-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="742ca-110">Gdy użytkownik wywołuje `ApplyBoth` ten przykład nad wynikiem operacji, będzie zależeć od kolejności `op1` i `op2` wewnątrz `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="742ca-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="742ca-111">Nie jest to termin oczekiwany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="742ca-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="742ca-112">`Distinct Inputs Checker`Program wykryje takie sytuacje, gdy zostanie włączone i wygeneruje `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="742ca-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="742ca-113">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="742ca-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="742ca-114">Korzystanie z narzędzia sprawdzania różnych wejść w programie w języku C#</span><span class="sxs-lookup"><span data-stu-id="742ca-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="742ca-115">Poniżej znajduje się przykładowy kod sterownika C# używany do korzystania z symulatora śledzenia komputerów Quantum z `Distinct Inputs Checker` włączonymi:</span><span class="sxs-lookup"><span data-stu-id="742ca-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="742ca-116">Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów Quantum i może być określona jako argument dla `QCTraceSimulator` konstruktora.</span><span class="sxs-lookup"><span data-stu-id="742ca-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="742ca-117">Gdy `useDistinctInputsChecker` ma wartość true, `Distinct Inputs Checker` jest włączona.</span><span class="sxs-lookup"><span data-stu-id="742ca-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="742ca-118">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="742ca-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="742ca-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="742ca-119">See also</span></span>

- <span data-ttu-id="742ca-120">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="742ca-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
