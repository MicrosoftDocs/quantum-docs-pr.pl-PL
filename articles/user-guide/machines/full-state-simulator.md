---
title: Pełny stan symulatora Quantum — zestaw Quantum Development Kit
description: Dowiedz się, jak uruchamiać Q# programy na Microsoft Quantum Development Kit symulatorze stanu pełnego.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992227"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Zestaw Quantum Development Kit (QDK) — symulator stanu pełnego

QDK zapewnia pełen symulatora stanu, który symuluje maszynę Quantum na komputerze lokalnym. Za pomocą symulatora stanu pełnego można uruchamiać i debugować algorytmy Quantum Q# , wykorzystując do 30 qubits. Pełen symulator stanu jest podobny do symulatora Quantum używanego w  [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformy Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Wywoływanie i uruchamianie symulatora stanu pełnego

Uwidaczniasz pełny symulator stanu za pośrednictwem `QuantumSimulator` klasy. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).

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

Użyj metody [symulacja ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Q# Python z zaimportowaną Q# operacją:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Wywoływanie symulatora z wiersza polecenia

W przypadku uruchamiania Q# programu z wiersza polecenia symulator stanu pełni jest domyślną maszyną docelową. Opcjonalnie można użyć parametru **--symulatora** (lub **-s** ), aby określić odpowiednią maszynę docelową. Oba poniższe polecenia uruchamiają program przy użyciu symulatora stanu pełnego. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Wywoływanie symulatora z notesów Juptyer

Użyj I Q# Magic polecenia [% symulacja](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić Q# operację.

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

## <a name="see-also"></a>Zobacz też

- [Narzędzie do szacowania zasobów kwantowych](xref:microsoft.quantum.machines.resources-estimator)
- [Kwantowy symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)