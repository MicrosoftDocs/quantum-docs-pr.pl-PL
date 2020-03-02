---
title: Symulator śledzenia komputera kwantowego
description: Dowiedz się, jak za pomocą symulatora śledzenia komputera kwantowego firmy Microsoft debugować klasyczny kod i szacować wymagania na zasoby programu kwantowego.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906087"
---
# <a name="quantum-trace-simulator"></a>Symulator śledzenia kwantowego

Symulator śledzenia komputera kwantowego firmy Microsoft umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego.  Pozwala to symulatorowi śledzenia wykonywać programy kwantowe korzystające z tysięcy kubitów.  Wyróżniamy dwa główne zastosowania takiego symulatora: 

* Debugowanie kodu klasycznego, który jest częścią programu kwantowego. 
* Szacowanie zasobów wymaganych do uruchomienia danego wystąpienia programu kwantowego na komputerze kwantowym.

W przypadku konieczności wykonywania pomiarów symulator śledzenia korzysta z dodatkowych informacji podawanych przez użytkownika. Aby uzyskać więcej informacji na ten temat, zobacz sekcję [Podawanie prawdopodobieństwa wyników pomiarów](#providing-the-probability-of-measurement-outcomes). 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Podawanie prawdopodobieństwa wyników pomiarów

W algorytmach kwantowych są używane dwa rodzaje pomiarów. Pierwszy odgrywa rolę pomocniczą — użytkownik zazwyczaj zna prawdopodobieństwo wystąpienia wyników. W takim przypadku użytkownik może napisać operację <xref:microsoft.quantum.intrinsic.assertprob> w przestrzeni nazw <xref:microsoft.quantum.intrinsic>, aby udostępnić te informacje. Zostało to przedstawione w poniższym przykładzie:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Gdy symulator śledzenia wykona operację `AssertProb`, zarejestruje wynik `Zero` dla wartości `PauliZ` w elementach `source` i `q` z prawdopodobieństwem 0,5. Gdy symulator wykona później operację `M`, znajdzie zarejestrowane wartości prawdopodobieństwa wyników, a operacja `M` zwróci element `Zero` lub `One` z prawdopodobieństwem 0,5. Jeśli ten sam kod zostanie wykonany w symulatorze, który śledzi stan kwantowy, symulator sprawdzi, czy prawdopodobieństwa podane w operacji `AssertProb` są poprawne.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Uruchamianie programu za pomocą symulatora śledzenia komputera kwantowego 

Symulator śledzenia komputera kwantowego można traktować jako zwykłą maszynę docelową. Program sterujący w języku C# umożliwiający korzystania z symulatora jest bardzo podobny do programu dla dowolnego innego symulatora kwantowego: 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Należy pamiętać, że jeśli istnieje co najmniej jeden pomiar nieopisany przy użyciu operacji `AssertProb`, symulator zgłosi wyjątek `UnconstrainedMeasurementException` w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Aby uzyskać więcej informacji, zobacz dokumentację interfejsu API dotyczącą wyjątku [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).

Symulator śledzenia nie tylko pozwala uruchamiać programy kwantowe. Zawiera on pięć składników, które umożliwiają wykrywanie usterek w programach i wykonywanie oszacowań zasobów programu kwantowego: 

* [Narzędzie do sprawdzania odrębnych danych wejściowych](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Narzędzie do sprawdzania użycia nieprawidłowych kubitów](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Licznik operacji pierwotnych](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Licznik głębokości obwodu](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Licznik szerokości obwodu](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Poszczególne składniki włącza się, ustawiając odpowiednie flagi w klasie `QCTraceSimulatorConfiguration`. Więcej informacji o używaniu tych składników można znaleźć w odpowiednich plikach dokumentacji. Aby uzyskać szczegółowe informacje, zobacz dokumentację interfejsu API dotyczącą klasy [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="see-also"></a>Zobacz też
Dokumentacja [symulatora śledzenia](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) komputera kwantowego dla języka C# 

