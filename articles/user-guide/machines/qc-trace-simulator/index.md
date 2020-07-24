---
title: Symulator śledzenia kwantowego — zestaw Quantum Development Kit
description: Dowiedz się, jak za pomocą symulatora śledzenia komputera kwantowego firmy Microsoft debugować klasyczny kod i szacować wymagania dotyczące zasobów programu w języku Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871114"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Symulator śledzenia kwantowego zestawu Microsoft Quantum Development Kit (QDK)

Klasa <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> zestawu QDK uruchamia program kwantowy bez faktycznego symulowania stanu komputera kwantowego. Pozwala to symulatorowi śledzenia kwantowego wykonywać programy kwantowe korzystające z tysięcy kubitów.  Wyróżniamy dwa główne zastosowania takiego symulatora: 

* Debugowanie kodu klasycznego, który jest częścią programu kwantowego. 
* Szacowanie zasobów wymaganych do uruchomienia danego wystąpienia programu kwantowego na komputerze kwantowym. W rzeczywistości [narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator) zapewniające bardziej ograniczony zestaw metryk jest oparte na symulatorze śledzenia.

## <a name="invoking-the-quantum-trace-simulator"></a>Wywoływanie symulatora śledzenia kwantowego

Za pomocą symulatora śledzenia kwantowego można uruchomić dowolną operację w języku Q#.

Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `QCTraceSimulator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.

Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `QCTraceSimulator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Podawanie prawdopodobieństwa wyników pomiarów

Ponieważ symulator śledzenia kwantowego nie symuluje rzeczywistego stanu kwantowego, nie może on obliczyć prawdopodobieństwa wyników pomiaru w ramach operacji. 

W związku z tym jeśli operacja obejmuje pomiary, należy jawnie podać te prawdopodobieństwa przy użyciu operacji <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z przestrzeni nazw <xref:microsoft.quantum.diagnostics>. Zostało to przedstawione w poniższym przykładzie:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Gdy symulator śledzenia kwantowego napotka element `AssertMeasurementProbability`, zarejestruje wynik `Zero` dla wartości `PauliZ` w elementach `source` i `q` z prawdopodobieństwem **0.5**. Po uruchomieniu później operacji `M` symulator odnajdzie zarejestrowane wartości prawdopodobieństwa wyniku, a operacja `M` zwróci wartość `Zero` lub `One` z prawdopodobieństwem **0.5**. Jeśli ten sam kod zostanie wykonany w symulatorze, który śledzi stan kwantowy, taki symulator sprawdzi, czy prawdopodobieństwa podane w operacji `AssertMeasurementProbability` są poprawne.

Należy pamiętać, że jeśli istnieje co najmniej jedna operacja pomiaru nieopisana przy użyciu elementu `AssertMeasurementProbability`, symulator zgłosi wyjątek [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Narzędzia symulatora śledzenia kwantowego

Zestaw QDK obejmuje pięć narzędzi, których można używać z symulatorem śledzenia kwantowego do wykrywania usterek w programach i wykonywania szacowania zasobów programu kwantowego: 

|Narzędzie | Opis |
|-----| -----|
|[Narzędzie do sprawdzania odrębnych danych wejściowych](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Sprawdza potencjalne konflikty z współdzielonymi kubitami |
|[Narzędzie do sprawdzania użycia unieważnionych kubitów](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Sprawdza, czy program stosuje operację względem kubitu, który został już zwolniony |
|[Licznik operacji pierwotnych](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie kwantowym  |
|[Licznik głębokości](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Zbiera liczniki reprezentujące dolną granicę głębokości każdej operacji wywołanej w programie kwantowym   |
|[Licznik szerokości](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Zlicza liczbę kubitów przydzieloną i zapożyczoną przez każdą operację w programie kwantowym |

Każde z tych narzędzi jest włączane przez ustawienie odpowiednich flag w konfiguracji `QCTraceSimulatorConfiguration`, a następnie przekazanie konfiguracji do deklaracji programu `QCTraceSimulator`. Aby uzyskać informacje na temat korzystania z każdego z tych narzędzi, zobacz linki na powyższej liście. Aby uzyskać więcej informacji na temat konfigurowania programu `QCTraceSimulator`, zobacz [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Metody programu QCTraceSimulator

Program `QCTraceSimulator` ma kilka wbudowanych metod służących do pobierania wartości metryk śledzonych podczas operacji kwantowej. Przykłady metod [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) i [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) można znaleźć w artykułach [Licznik operacji pierwotnych](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Licznik głębokości](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) i [Licznik szerokości](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Aby uzyskać więcej informacji na temat wszystkich dostępnych metod, zobacz [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) w dokumentacji interfejsu API języka Q#.  

## <a name="see-also"></a>Zobacz też

- [Narzędzie do szacowania zasobów kwantowych](xref:microsoft.quantum.machines.resources-estimator)
- [Kwantowy symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kwantowy symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator) 