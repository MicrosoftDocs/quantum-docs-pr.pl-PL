---
title: Unieważniony qubits użycie modułu sprawdzania dla zestawu Quantum Development Kit
description: Dowiedz się więcej na temat programu Microsoft QDK unieważniony qubits użycia narzędzia sprawdzania poprawności, które korzysta z symulatora śledzenia Quantum do sprawdzenia Q# kodu dla potencjalnie nieprawidłowego qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9014097ace7c9f19d93a92372da40f71fa7f87ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858620"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Symulator śledzenia Quantum: unieważniony qubits użycia

Sprawdzanie poprawności użycia qubits jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit. Można jej użyć do wykrywania potencjalnych usterek w kodzie spowodowanym przez nieprawidłowe qubits. 

## <a name="invalid-qubits"></a>Nieprawidłowy qubits

Rozważmy następujący fragment Q# kodu, aby zilustrować problemy wykryte przez unieważniony moduł sprawdzania poprawności qubits:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Po zastosowaniu `H` operacji do `q[0]` , wskazuje już wydaną qubit, co może spowodować niezdefiniowane zachowanie. Gdy jest włączony moduł sprawdzania poprawności Qubits, zgłasza wyjątek, `InvalidatedQubitsUseCheckerException` Jeśli program zastosuje operację do już wydanego qubit. Aby uzyskać więcej informacji, zobacz <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Wywoływanie niezweryfikowanego użycia narzędzia qubits

Aby uruchomić symulator śledzenia Quantum z niezweryfikowanym użyciem qubits, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseInvalidatedQubitsUseChecker` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Używanie narzędzia sprawdzania poprawności qubits w programie hosta C#

Poniżej znajduje się przykład programów hostów języka C#, które korzystają z symulatora śledzenia Quantum z włączonym sprawdzaniem poprawności qubits użycia: 

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

## <a name="see-also"></a>Zobacz także

- Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>Dokumentacja interfejsu API.
