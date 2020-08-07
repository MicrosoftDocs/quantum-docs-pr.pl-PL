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
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Symulator śledzenia Quantum: unikatowe dane wejściowe

Narzędzie sprawdzania odrębnych danych wejściowych jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit. Można jej użyć do wykrywania potencjalnych usterek w kodzie spowodowanym konfliktami z współdzielonym qubits. 

## <a name="conflicts-with-shared-qubits"></a>Konflikty z współdzielonym qubits

Rozważmy następujący fragment Q# kodu do zilustrowania problemów wykrytych przez narzędzie sprawdzania różnych wejść:

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

Podczas przeglądania tego programu można założyć, że kolejność, w jakiej jest wywoływana `op1` , i nie ma `op2` znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch. 

Teraz Rozważmy następujący przykład:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Należy pamiętać, że `op1` `op2` są one zarówno uzyskiwane przy użyciu częściowej aplikacji, jak i udostępniają qubit. Gdy wywołujesz `ApplyBoth` w tym przykładzie, wynik operacji zależy od kolejności `op1` i wewnątrz, a `op2` nie od `ApplyBoth` oczekiwanego. Po włączeniu sprawdzania odrębnych wejść wykrywa takie sytuacje i zgłasza `DistinctInputsCheckerException` . Aby uzyskać więcej informacji, zobacz sekcję <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> w Q# bibliotece interfejsu API.

## <a name="invoking-the-distinct-inputs-checker"></a>Wywoływanie narzędzia sprawdzania różnych wejść

Aby uruchomić symulator śledzenia funkcji Quantum za pomocą narzędzia sprawdzania różnych wejść, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseDistinctInputsChecker` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Korzystanie z narzędzia sprawdzania różnych wejść w programie hosta C#

Poniżej znajduje się przykład programu hosta języka C#, który używa symulatora śledzenia Quantum z włączonym modułem sprawdzania odrębnych wejść:

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

## <a name="see-also"></a>Zobacz także

- Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>Dokumentacja interfejsu API.
