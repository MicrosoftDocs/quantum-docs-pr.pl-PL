---
title: Quantum Toffoli symulator — Quantum Development Kit
description: Dowiedz się więcej o symulatorze Microsoft QDK Toffoli, w specjalnym symulatorze Quantum, który może być używany z milionami qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690779"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Zestaw Quantum Development Kit (QDK) Toffoli symulator

Symulator QDK Toffoli jest symulatorem specjalnym z ograniczonym zakresem i obsługuje tylko `X` i obsługują `CNOT` wielokontrolowane `X` operacje Quantum. Wszystkie klasyczne logiki i obliczenia są dostępne.

Chociaż symulator Toffoli jest bardziej ograniczony w funkcjonalności niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), zaletą jest możliwość symulowania znacznie większej liczby qubits. Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ograniczony do około 30 qubits. Jest to przydatne, na przykład w przypadku systemów Oracle, które obliczają funkcje logiczne — można zaimplementować przy użyciu ograniczonego zestawu obsługiwanych algorytmów i przetestowanych na dużą liczbę qubits.

## <a name="invoking-the-toffoli-simulator"></a>Wywoływanie symulatora Toffoli

Symulator Toffoli można uwidocznić za pośrednictwem `ToffoliSimulator` klasy. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Wywoływanie symulatora Toffoli z języka C #

Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `ToffoliSimulator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.

Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `ToffoliSimulator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Wywoływanie symulatora Toffoli z poziomu języka Python

Użyj metody [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną Q# operacją:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Wywoływanie symulatora Toffoli z wiersza polecenia

Podczas uruchamiania Q# programu z wiersza polecenia, użyj parametru **--symulatora** (lub **-s** skrótu), aby określić komputer docelowy symulatora Toffoli. Następujące polecenie uruchamia program przy użyciu szacowania zasobów: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Wywoływanie symulatora Toffoli z notesów Juptyer

Użyj I Q# Magic polecenia [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) , aby uruchomić Q# operację.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Obsługiwane operacje

Symulator Toffoli obsługuje:

* Rotacje i exponentiated Pauly, takie jak `R` i `Exp` , gdy wynikiem operacji jest równa `X` się lub macierzy tożsamości.
* Operacje pomiarów i [potwierdzeń](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) , ale tylko na `Z` podstawie Pauli. Zwróć uwagę, że prawdopodobieństwo operacji pomiaru ma zawsze **wartość 0** lub **1** ; nie ma losowości w symulatorze Toffoli.
* `DumpMachine` i `DumpRegister` funkcje.
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