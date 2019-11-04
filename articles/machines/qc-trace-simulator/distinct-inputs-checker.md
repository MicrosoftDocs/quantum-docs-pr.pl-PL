---
title: Sprawdzanie odrębnych wejść | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputerów z interfejsem Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 0df28f6d74279db4678c3485a23a9341680eec52
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184699"
---
# <a name="distinct-inputs-checker"></a>Sprawdzanie odrębnych wejść

`Distinct Inputs Checker` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum. Jest ona przeznaczona do wykrywania potencjalnych usterek w kodzie. Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez ten pakiet:

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

Gdy użytkownik przegląda ten program, zakłada, że kolejność, w której `op1` i `op2` są wywoływane, nie ma znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch. Teraz Rozważmy przykład, w którym ta operacja jest używana:

```qsharp
operation DisctinctQubitCaptured2Test () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

Teraz `op1` i `op2` są uzyskane przy użyciu częściowej aplikacji i udostępniają qubit. Gdy użytkownik wywołuje `DoBoth` w przykładzie powyżej wyniku operacji, będzie zależeć od kolejności `op1` i `op2` w `DoBoth`. Nie jest to termin oczekiwany przez użytkownika. `Distinct Inputs Checker` wykryje takie sytuacje, gdy zostanie włączone i zgłosi `DistinctInputsCheckerException`. Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Korzystanie z narzędzia sprawdzania różnych wejść w C# programie

Poniżej znajduje się przykładowy kod C# sterownika służący do korzystania z symulatora śledzenia komputerów Quantum z włączonym `Distinct Inputs Checker`:

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

Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów z Quantum i może być określona jako argument dla konstruktora `QCTraceSimulator`. Gdy `useDistinctInputsChecker` ma wartość true, `Distinct Inputs Checker` jest włączona. Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Zobacz także

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.
