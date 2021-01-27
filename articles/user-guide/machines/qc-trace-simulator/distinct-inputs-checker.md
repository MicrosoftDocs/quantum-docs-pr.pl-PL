---
title: Sprawdzanie odrębnych wejść — zestaw Quantum Development Kit
description: Dowiedz się więcej o programie Microsoft QDK DISTINCT Input Checker, który używa symulatora śledzenia usługi Quantum do sprawdzenia Q# kodu pod kątem potencjalnych konfliktów z współdzielonym qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8076a705b1960ae8e23be4cea87e613329a24f77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858658"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="5fb14-103">Symulator śledzenia Quantum: unikatowe dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5fb14-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="5fb14-104">Narzędzie sprawdzania odrębnych danych wejściowych jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="5fb14-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="5fb14-105">Można jej użyć do wykrywania potencjalnych usterek w kodzie spowodowanym konfliktami z współdzielonym qubits.</span><span class="sxs-lookup"><span data-stu-id="5fb14-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="5fb14-106">Konflikty z współdzielonym qubits</span><span class="sxs-lookup"><span data-stu-id="5fb14-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="5fb14-107">Rozważmy następujący fragment Q# kodu do zilustrowania problemów wykrytych przez narzędzie sprawdzania różnych wejść:</span><span class="sxs-lookup"><span data-stu-id="5fb14-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="5fb14-108">Podczas przeglądania tego programu można założyć, że kolejność, w jakiej jest wywoływana `op1` , i nie ma `op2` znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch.</span><span class="sxs-lookup"><span data-stu-id="5fb14-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="5fb14-109">Teraz Rozważmy następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="5fb14-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="5fb14-110">Należy pamiętać, że `op1` `op2` są one zarówno uzyskiwane przy użyciu częściowej aplikacji, jak i udostępniają qubit.</span><span class="sxs-lookup"><span data-stu-id="5fb14-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="5fb14-111">Gdy wywołujesz `ApplyBoth` w tym przykładzie, wynik operacji zależy od kolejności `op1` i wewnątrz, a `op2` nie od `ApplyBoth` oczekiwanego.</span><span class="sxs-lookup"><span data-stu-id="5fb14-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="5fb14-112">Po włączeniu sprawdzania odrębnych wejść wykrywa takie sytuacje i zgłasza `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="5fb14-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="5fb14-113">Aby uzyskać więcej informacji, zobacz sekcję <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> w Q# bibliotece interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="5fb14-113">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="5fb14-114">Wywoływanie narzędzia sprawdzania różnych wejść</span><span class="sxs-lookup"><span data-stu-id="5fb14-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="5fb14-115">Aby uruchomić symulator śledzenia funkcji Quantum za pomocą narzędzia sprawdzania różnych wejść, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseDistinctInputsChecker` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="5fb14-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="5fb14-116">Korzystanie z narzędzia sprawdzania różnych wejść w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="5fb14-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="5fb14-117">Poniżej znajduje się przykład programu hosta języka C#, który używa symulatora śledzenia Quantum z włączonym modułem sprawdzania odrębnych wejść:</span><span class="sxs-lookup"><span data-stu-id="5fb14-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="5fb14-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5fb14-118">See also</span></span>

- <span data-ttu-id="5fb14-119">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="5fb14-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="5fb14-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="5fb14-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="5fb14-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="5fb14-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="5fb14-122"><xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="5fb14-122">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> API reference.</span></span>
