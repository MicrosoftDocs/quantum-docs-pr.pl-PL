---
title: Zestaw Quantum Development Kit Toffoli symulator
description: Dowiedz się więcej o symulatorze Microsoft QDK Toffoli, w specjalnym symulatorze Quantum, który może być używany z milionami qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276031"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Zestaw Quantum Development Kit Toffoli symulator

Zestaw Quantum Development Kit udostępnia Toffoli symulator, który jest symulatorem o specjalnym przeznaczeniu, który może symulować algorytmy Quantum, które są ograniczone do operacji X, CNOT i wielokontrolowanej kontroli X Quantum (wszystkie klasyczne logiki i obliczenia są dostępne).

Gdy symulator Toffoli jest znacznie bardziej ograniczony w operacji niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), może symulować dużo więcej qubits.
Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ogólnie ograniczony do około 30.
Może wykonywać i debugować ograniczony zestaw algorytmów Quantum, które są zapisywane w Q # na komputerze; na przykład firmy Oracle, które obliczają funkcje logiczne, można zaimplementować przy użyciu tych bram i sprawdzać się na różnych qubitsach przy użyciu tego symulatora.

Ten symulator Quantum jest udostępniany za pośrednictwem `ToffoliSimulator` klasy.
Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do `Run` metody operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Inne operacje

`ToffoliSimulator`Obsługuje rotacje i Exponentiated Paul, takie jak `R` i `Exp` , gdy wynikiem operacji jest równa `X` lub do tożsamości.

Pomiar i potwierdzenie są obsługiwane, ale tylko w Pauli `Z` .
Należy zauważyć, że prawdopodobieństwo pewnej miary ma zawsze wartość 0 lub 1; nie ma losowości w symulatorze Toffoli.

`DumpMachine`i `DumpRegister` są obsługiwane.
Oba te elementy są wyprowadzane w bieżącym `Z` stanie każdego qubitu, jedną qubit na wiersz.

## <a name="qubitcount"></a>QubitCount

Domyślnie `ToffoliSimulator` przypisuje miejsce dla 65 536 qubits.
Jeśli algorytm wymaga więcej niż ten, można zmienić liczbę qubit, podając wartość `qubitCount` parametru konstruktora.
Każdy dodatkowy qubit wymaga dodatkowego bajtu pamięci, więc nie ma znaczącego kosztu oszacowania liczby potrzebnych qubits.

Przykład:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
