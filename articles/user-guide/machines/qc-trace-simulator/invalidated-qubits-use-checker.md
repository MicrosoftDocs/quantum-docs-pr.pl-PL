---
title: Unieważniony qubits użycie modułu sprawdzania dla zestawu Quantum Development Kit
description: 'Dowiedz się więcej na temat programu Microsoft QDK unieważniony qubits use test, który korzysta z symulatora śledzenia Quantum do sprawdzenia kodu Q # dla potencjalnie nieprawidłowego qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871097"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="0697c-103">Symulator śledzenia Quantum: unieważniony qubits użycia</span><span class="sxs-lookup"><span data-stu-id="0697c-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="0697c-104">Sprawdzanie poprawności użycia qubits jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="0697c-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0697c-105">Można jej użyć do wykrywania potencjalnych usterek w kodzie spowodowanym przez nieprawidłowe qubits.</span><span class="sxs-lookup"><span data-stu-id="0697c-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="0697c-106">Nieprawidłowy qubits</span><span class="sxs-lookup"><span data-stu-id="0697c-106">Invalid qubits</span></span>

<span data-ttu-id="0697c-107">Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez unieważniony qubits użycia narzędzia sprawdzania poprawności:</span><span class="sxs-lookup"><span data-stu-id="0697c-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="0697c-108">Po zastosowaniu `H` operacji do `q[0]` , wskazuje już wydaną qubit, co może spowodować niezdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="0697c-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="0697c-109">Gdy jest włączony moduł sprawdzania poprawności Qubits, zgłasza wyjątek, `InvalidatedQubitsUseCheckerException` Jeśli program zastosuje operację do już wydanego qubit.</span><span class="sxs-lookup"><span data-stu-id="0697c-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="0697c-110">Aby uzyskać więcej informacji, zobacz <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="0697c-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="0697c-111">Wywoływanie niezweryfikowanego użycia narzędzia qubits</span><span class="sxs-lookup"><span data-stu-id="0697c-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="0697c-112">Aby uruchomić symulator śledzenia Quantum z niezweryfikowanym użyciem qubits, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseInvalidatedQubitsUseChecker` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="0697c-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="0697c-113">Używanie narzędzia sprawdzania poprawności qubits w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="0697c-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="0697c-114">Poniżej znajduje się przykład programów hostów języka C#, które korzystają z symulatora śledzenia Quantum z włączonym sprawdzaniem poprawności qubits użycia:</span><span class="sxs-lookup"><span data-stu-id="0697c-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="0697c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0697c-115">See also</span></span>

- <span data-ttu-id="0697c-116">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="0697c-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="0697c-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="0697c-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="0697c-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="0697c-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="0697c-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="0697c-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>