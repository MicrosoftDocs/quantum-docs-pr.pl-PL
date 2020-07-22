---
title: Pełny stan symulatora Quantum — zestaw Quantum Development Kit
description: 'Dowiedz się, jak uruchamiać programy Q # na Microsoft Quantum Development Kit symulatorze pełnego stanu.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871182"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Zestaw Quantum Development Kit (QDK) — symulator stanu pełnego

QDK zapewnia pełen symulatora stanu, który symuluje maszynę Quantum na komputerze lokalnym. Za pomocą symulatora stanu pełnego można uruchamiać i debugować algorytmy Quantum w języku Q #, wykorzystując do 30 qubits. Pełen symulator stanu jest podobny do symulatora Quantum używanego w [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformy Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Wywoływanie i uruchamianie symulatora stanu pełnego

Uwidaczniasz pełny symulator stanu za pośrednictwem `QuantumSimulator` klasy. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania programu Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Wywoływanie symulatora z C #

Utwórz wystąpienie `QuantumSimulator` klasy, a następnie Przekaż je do `Run` metody operacji Quantum, wraz z wszelkimi dodatkowymi parametrami.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Ponieważ `QuantumSimulator` Klasa implementuje <xref:System.IDisposable> interfejs, należy wywołać `Dispose` metodę, gdy nie jest już potrzebne wystąpienie symulatora. Najlepszym sposobem jest otoczenie deklaracji symulatora i operacji w instrukcji [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , która automatycznie wywołuje `Dispose` metodę.

### <a name="invoking-the-simulator-from-python"></a>Wywoływanie symulatora z języka Python

Użyj metody [symulacja ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Python q # z zaimportowaną operacją q #:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Wywoływanie symulatora z wiersza polecenia

W przypadku uruchamiania programu Q # z wiersza polecenia symulator stanu pełnego jest domyślną maszyną docelową. Opcjonalnie można użyć parametru **--symulatora** (lub **-s** ), aby określić odpowiednią maszynę docelową. Oba poniższe polecenia uruchamiają program przy użyciu symulatora stanu pełnego. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Wywoływanie symulatora z notesów Juptyer

Użyj polecenia IQ # Magic [% symulacja](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić operację Q #.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Rozmieszczanie symulatora

Domyślnie symulator o pełnym stanie używa generatora liczb losowych do symulowania losowości Quantum. W celach testowych czasami warto mieć deterministyczne wyniki. W programie w języku C# można to zrobić, dostarczając inicjator dla generatora liczb losowych w `QuantumSimulator` konstruktorze za pośrednictwem `randomNumberGeneratorSeed` parametru.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Konfigurowanie wątków

W przypadku symulatora pełnego stanu do zrównoleglanie algebry liniowych wymagana jest funkcja [OpenMP](http://www.openmp.org/) . Domyślnie OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą qubits często działają powoli, ponieważ koordynacja, która jest wymagana Dwarfs rzeczywistej pracy. Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę. Jako regułę elementu kciuka skonfiguruj jeden wątek dla maksymalnie czterech qubits, a następnie jeden dodatkowy wątek na qubit. Może być konieczne dostosowanie zmiennej w zależności od algorytmu.

## <a name="see-also"></a>Zobacz także

- [Szacowania zasobów Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Symulator Toffoli Quantum](xref:microsoft.quantum.machines.toffoli-simulator)
- [Symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)