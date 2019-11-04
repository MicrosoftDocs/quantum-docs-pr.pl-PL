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
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="5a7de-103">Zestaw Quantum Development Kit Toffoli symulator</span><span class="sxs-lookup"><span data-stu-id="5a7de-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="5a7de-104">Zestaw Quantum Development Kit udostępnia Toffoli symulator, który jest symulatorem o specjalnym przeznaczeniu, który może symulować algorytmy Quantum, które są ograniczone do operacji X, CNOT i wielokontrolowanej kontroli X Quantum (wszystkie klasyczne logiki i obliczenia są dostępne).</span><span class="sxs-lookup"><span data-stu-id="5a7de-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="5a7de-105">Gdy symulator Toffoli jest znacznie bardziej ograniczony w operacji niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), może symulować dużo więcej qubits.</span><span class="sxs-lookup"><span data-stu-id="5a7de-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="5a7de-106">Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ogólnie ograniczony do około 30.</span><span class="sxs-lookup"><span data-stu-id="5a7de-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="5a7de-107">Może wykonywać i debugować ograniczony zestaw algorytmów Quantum, które są zapisywane w Q # na komputerze; na przykład firmy Oracle, które obliczają funkcje logiczne, można zaimplementować przy użyciu tych bram i sprawdzać się na różnych qubitsach przy użyciu tego symulatora.</span><span class="sxs-lookup"><span data-stu-id="5a7de-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="5a7de-108">Ten symulator Quantum jest udostępniany za pośrednictwem klasy `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="5a7de-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="5a7de-109">Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do metody `Run` operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:</span><span class="sxs-lookup"><span data-stu-id="5a7de-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="5a7de-110">Inne operacje</span><span class="sxs-lookup"><span data-stu-id="5a7de-110">Other Operations</span></span>

<span data-ttu-id="5a7de-111">`ToffoliSimulator` obsługuje rotacje i exponentiated Paul, takie jak `R` i `Exp`, gdy wynikiem operacji jest równa `X` lub do tożsamości.</span><span class="sxs-lookup"><span data-stu-id="5a7de-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="5a7de-112">Pomiar i potwierdzenie są obsługiwane, ale tylko w `Z` Pauli.</span><span class="sxs-lookup"><span data-stu-id="5a7de-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="5a7de-113">Należy zauważyć, że prawdopodobieństwo pewnej miary ma zawsze wartość 0 lub 1; nie ma losowości w symulatorze Toffoli.</span><span class="sxs-lookup"><span data-stu-id="5a7de-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="5a7de-114">Obsługiwane są `DumpMachine` i `DumpRegister`.</span><span class="sxs-lookup"><span data-stu-id="5a7de-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="5a7de-115">Oba te elementy są wyprowadzane na podstawie bieżącego `Z`każdego qubitu, jednego qubit w każdym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5a7de-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="5a7de-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="5a7de-116">QubitCount</span></span>

<span data-ttu-id="5a7de-117">Domyślnie `ToffoliSimulator` przydziela miejsce na 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="5a7de-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="5a7de-118">Jeśli algorytm wymaga więcej niż ten, można zmienić liczbę qubit, podając wartość dla parametru `qubitCount` konstruktora.</span><span class="sxs-lookup"><span data-stu-id="5a7de-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="5a7de-119">Każdy dodatkowy qubit wymaga dodatkowego bajtu pamięci, więc nie ma znaczącego kosztu oszacowania liczby potrzebnych qubits.</span><span class="sxs-lookup"><span data-stu-id="5a7de-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="5a7de-120">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5a7de-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
