---
title: Zestaw Quantum Development Kit Toffoli symulator | Microsoft Docs
description: Przegląd zestawu Microsoft Quantum Development Kit Toffoli symulator
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442346"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Zestaw Quantum Development Kit Toffoli symulator

Zestaw Quantum Development Kit udostępnia Toffoli symulator, który jest symulatorem o specjalnym przeznaczeniu, który może symulować algorytmy Quantum, które są ograniczone do operacji X, CNOT i wielokontrolowanej kontroli X Quantum (wszystkie klasyczne logiki i obliczenia są dostępne).

Gdy symulator Toffoli jest znacznie bardziej ograniczony w operacji niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), może symulować dużo więcej qubits.
Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ogólnie ograniczony do około 30.
Może wykonywać i debugować ograniczony zestaw algorytmów Quantum, które są zapisywane w Q # na komputerze; na przykład firmy Oracle, które obliczają funkcje logiczne, można zaimplementować przy użyciu tych bram i sprawdzać się na różnych qubitsach przy użyciu tego symulatora.

Ten symulator Quantum jest udostępniany za pośrednictwem klasy `ToffoliSimulator`.
Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do metody `Run` operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Inne operacje

`ToffoliSimulator` obsługuje rotacje i exponentiated Paul, takie jak `R` i `Exp`, gdy wynikiem operacji jest równa `X` lub do tożsamości.

Pomiar i potwierdzenie są obsługiwane, ale tylko w `Z` Pauli.
Należy zauważyć, że prawdopodobieństwo pewnej miary ma zawsze wartość 0 lub 1; nie ma losowości w symulatorze Toffoli.

Obsługiwane są `DumpMachine` i `DumpRegister`.
Oba te elementy są wyprowadzane na podstawie bieżącego `Z`każdego qubitu, jednego qubit w każdym wierszu.

## <a name="qubitcount"></a>QubitCount

Domyślnie `ToffoliSimulator` przydziela miejsce na 65 536 qubits.
Jeśli algorytm wymaga więcej niż ten, można zmienić liczbę qubit, podając wartość dla parametru `qubitCount` konstruktora.
Każdy dodatkowy qubit wymaga dodatkowego bajtu pamięci, więc nie ma znaczącego kosztu oszacowania liczby potrzebnych qubits.

Na przykład:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
