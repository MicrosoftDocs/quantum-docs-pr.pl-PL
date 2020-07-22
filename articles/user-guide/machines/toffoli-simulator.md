---
title: Quantum Toffoli symulator — Quantum Development Kit
description: Dowiedz się więcej o symulatorze Microsoft QDK Toffoli, w specjalnym symulatorze Quantum, który może być używany z milionami qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870621"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Zestaw Quantum Development Kit (QDK) Toffoli symulator

Symulator QDK Toffoli jest symulatorem specjalnym z ograniczonym zakresem i obsługuje tylko `X` i obsługują `CNOT` wielokontrolowane `X` operacje Quantum. Wszystkie klasyczne logiki i obliczenia są dostępne.

Chociaż symulator Toffoli jest bardziej ograniczony w funkcjonalności niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), zaletą jest możliwość symulowania znacznie większej liczby qubits. Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ograniczony do około 30 qubits. Jest to przydatne, na przykład w przypadku systemów Oracle, które obliczają funkcje logiczne — można zaimplementować przy użyciu ograniczonego zestawu obsługiwanych algorytmów i przetestowanych na dużą liczbę qubits.

## <a name="invoking-the-toffoli-simulator"></a>Wywoływanie symulatora Toffoli

Symulator Toffoli można uwidocznić za pośrednictwem `ToffoliSimulator` klasy. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania programu Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Wywoływanie symulatora Toffoli z języka C #

Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie `ToffoliSimulator` klasy, a następnie przekazać je jako pierwszy parametr `Run` metody operacji.

Należy pamiętać, że w przeciwieństwie do `QuantumSimulator` klasy `ToffoliSimulator` Klasa nie implementuje <xref:System.IDisposable> interfejsu, dlatego nie trzeba go umieszczać w `using` instrukcji.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Wywoływanie symulatora Toffoli z poziomu języka Python

Użyj metody [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną operacją Q #:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Wywoływanie symulatora Toffoli z wiersza polecenia

Podczas uruchamiania programu Q # z wiersza polecenia, użyj parametru **--symulatora** (lub **-s** ), aby określić komputer docelowy symulatora Toffoli. Następujące polecenie uruchamia program przy użyciu szacowania zasobów: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Wywoływanie symulatora Toffoli z notesów Juptyer

Użyj polecenia IQ # Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) , aby uruchomić operację Q #.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Obsługiwane operacje

Symulator Toffoli obsługuje:

* Rotacje i exponentiated Pauly, takie jak `R` i `Exp` , gdy wynikiem operacji jest równa `X` się lub macierzy tożsamości.
* Operacje pomiarów i [potwierdzeń](xref:microsoft.quantum.diagnostics.assertmeasurement) , ale tylko na `Z` podstawie Pauli. Zwróć uwagę, że prawdopodobieństwo operacji pomiaru ma zawsze **wartość 0** lub **1**; nie ma losowości w symulatorze Toffoli.
* `DumpMachine`i `DumpRegister` funkcje.
Obie funkcje wyprowadzają bieżący `Z` stan bazowy każdego qubitu, jedną qubit na wiersz.

## <a name="specifying-the-number-of-qubits"></a>Określanie liczby qubits

Domyślnie `ToffoliSimulator` wystąpienie przydziela miejsce na 65 536 qubits.
Jeśli algorytm wymaga więcej qubits niż ten, można określić liczbę qubit, podając wartość `qubitCount` parametru do konstruktora.
Każdy dodatkowy qubit wymaga tylko jednego bajtu pamięci, więc nie ma znaczącego kosztu oszacowania liczby potrzebnych qubits.

Na przykład:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Zobacz także

- [Szacowania zasobów Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Symulator pełnego stanu Quantum](xref:microsoft.quantum.machines.full-state-simulator) 