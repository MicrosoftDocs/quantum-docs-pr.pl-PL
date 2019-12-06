---
title: Sprawdzanie odrębnych wejść | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: ce3f156a84a4509781a74c9276b953c79670a756
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864308"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="fd076-103">Sprawdzanie odrębnych wejść</span><span class="sxs-lookup"><span data-stu-id="fd076-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="fd076-104">`Distinct Inputs Checker` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd076-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="fd076-105">Jest ona przeznaczona do wykrywania potencjalnych usterek w kodzie.</span><span class="sxs-lookup"><span data-stu-id="fd076-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="fd076-106">Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez ten pakiet:</span><span class="sxs-lookup"><span data-stu-id="fd076-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="fd076-107">Gdy użytkownik przegląda ten program, zakłada, że kolejność, w której `op1` i `op2` są wywoływane, nie ma znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch.</span><span class="sxs-lookup"><span data-stu-id="fd076-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="fd076-108">Teraz Rozważmy przykład, w którym ta operacja jest używana:</span><span class="sxs-lookup"><span data-stu-id="fd076-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation CapturedQubits () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

<span data-ttu-id="fd076-109">Teraz `op1` i `op2` są uzyskane przy użyciu częściowej aplikacji i udostępniają qubit.</span><span class="sxs-lookup"><span data-stu-id="fd076-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="fd076-110">Gdy użytkownik wywołuje `DoBoth` w przykładzie powyżej wyniku operacji, będzie zależeć od kolejności `op1` i `op2` w `DoBoth`.</span><span class="sxs-lookup"><span data-stu-id="fd076-110">When the user calls `DoBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `DoBoth`.</span></span> <span data-ttu-id="fd076-111">Nie jest to termin oczekiwany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fd076-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="fd076-112">`Distinct Inputs Checker` wykryje takie sytuacje, gdy zostanie włączone i zgłosi `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="fd076-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="fd076-113">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="fd076-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="fd076-114">Korzystanie z narzędzia sprawdzania różnych wejść w C# programie</span><span class="sxs-lookup"><span data-stu-id="fd076-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="fd076-115">Poniżej znajduje się przykładowy kod C# sterownika służący do korzystania z symulatora śledzenia komputerów Quantum z włączonym `Distinct Inputs Checker`:</span><span class="sxs-lookup"><span data-stu-id="fd076-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="fd076-116">Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów z Quantum i może być określona jako argument dla konstruktora `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="fd076-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="fd076-117">Gdy `useDistinctInputsChecker` ma wartość true, `Distinct Inputs Checker` jest włączona.</span><span class="sxs-lookup"><span data-stu-id="fd076-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="fd076-118">Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="fd076-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd076-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd076-119">See also</span></span>

- <span data-ttu-id="fd076-120">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd076-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
