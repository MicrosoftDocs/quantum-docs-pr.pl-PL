---
title: Sprawdzanie odrębnych wejść — zestaw Quantum Development Kit
description: Dowiedz się więcej o programie Microsoft QDK DISTINCT Input Checker, który używa symulatora śledzenia usługi Quantum do sprawdzenia Q# kodu pod kątem potencjalnych konfliktów z współdzielonym qubits.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868274"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="6aa04-103">Symulator śledzenia Quantum: unikatowe dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6aa04-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="6aa04-104">Narzędzie sprawdzania odrębnych danych wejściowych jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="6aa04-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6aa04-105">Można jej użyć do wykrywania potencjalnych usterek w kodzie spowodowanym konfliktami z współdzielonym qubits.</span><span class="sxs-lookup"><span data-stu-id="6aa04-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="6aa04-106">Konflikty z współdzielonym qubits</span><span class="sxs-lookup"><span data-stu-id="6aa04-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="6aa04-107">Rozważmy następujący fragment Q# kodu do zilustrowania problemów wykrytych przez narzędzie sprawdzania różnych wejść:</span><span class="sxs-lookup"><span data-stu-id="6aa04-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="6aa04-108">Podczas przeglądania tego programu można założyć, że kolejność, w jakiej jest wywoływana `op1` , i nie ma `op2` znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch.</span><span class="sxs-lookup"><span data-stu-id="6aa04-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="6aa04-109">Teraz Rozważmy następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="6aa04-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="6aa04-110">Należy pamiętać, że `op1` `op2` są one zarówno uzyskiwane przy użyciu częściowej aplikacji, jak i udostępniają qubit.</span><span class="sxs-lookup"><span data-stu-id="6aa04-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="6aa04-111">Gdy wywołujesz `ApplyBoth` w tym przykładzie, wynik operacji zależy od kolejności `op1` i wewnątrz, a `op2` nie od `ApplyBoth` oczekiwanego.</span><span class="sxs-lookup"><span data-stu-id="6aa04-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="6aa04-112">Po włączeniu sprawdzania odrębnych wejść wykrywa takie sytuacje i zgłasza `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="6aa04-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="6aa04-113">Aby uzyskać więcej informacji, zobacz sekcję <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> w Q# bibliotece interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6aa04-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="6aa04-114">Wywoływanie narzędzia sprawdzania różnych wejść</span><span class="sxs-lookup"><span data-stu-id="6aa04-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="6aa04-115">Aby uruchomić symulator śledzenia funkcji Quantum za pomocą narzędzia sprawdzania różnych wejść, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseDistinctInputsChecker` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="6aa04-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="6aa04-116">Korzystanie z narzędzia sprawdzania różnych wejść w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="6aa04-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="6aa04-117">Poniżej znajduje się przykład programu hosta języka C#, który używa symulatora śledzenia Quantum z włączonym modułem sprawdzania odrębnych wejść:</span><span class="sxs-lookup"><span data-stu-id="6aa04-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6aa04-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6aa04-118">See also</span></span>

- <span data-ttu-id="6aa04-119">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="6aa04-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="6aa04-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6aa04-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="6aa04-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6aa04-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="6aa04-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6aa04-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
