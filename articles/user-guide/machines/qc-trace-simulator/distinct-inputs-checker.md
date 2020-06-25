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
# <a name="distinct-inputs-checker"></a>Sprawdzanie odrębnych wejść

`Distinct Inputs Checker`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum. Jest ona przeznaczona do wykrywania potencjalnych usterek w kodzie. Rozważmy następujący fragment kodu Q #, aby zilustrować problemy wykryte przez ten pakiet:

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

Gdy użytkownik przegląda ten program, zakłada, że kolejność, w której `op1` `op2` są wywoływane, nie ma znaczenia, ponieważ `q1` i `q2` są różne qubits i operacje działające na różnych qubitsch. Teraz Rozważmy przykład, w którym ta operacja jest używana:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Teraz `op1` i `op2` są one uzyskiwane przy użyciu częściowej aplikacji i udostępniają qubit. Gdy użytkownik wywołuje `ApplyBoth` ten przykład nad wynikiem operacji, będzie zależeć od kolejności `op1` i `op2` wewnątrz `ApplyBoth` . Nie jest to termin oczekiwany przez użytkownika. `Distinct Inputs Checker`Program wykryje takie sytuacje, gdy zostanie włączone i wygeneruje `DistinctInputsCheckerException` . Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w witrynie [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Korzystanie z narzędzia sprawdzania różnych wejść w programie w języku C#

Poniżej znajduje się przykładowy kod sterownika C# używany do korzystania z symulatora śledzenia komputerów Quantum z `Distinct Inputs Checker` włączonymi:

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

Klasa `QCTraceSimulatorConfiguration` przechowuje konfigurację symulatora śledzenia komputerów Quantum i może być określona jako argument dla `QCTraceSimulator` konstruktora. Gdy `useDistinctInputsChecker` ma wartość true, `Distinct Inputs Checker` jest włączona. Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API w systemach [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Zobacz też

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.
