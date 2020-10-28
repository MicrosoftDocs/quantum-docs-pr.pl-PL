---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710542"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="038c4-102">PauliStringFromGenIdx, funkcja</span><span class="sxs-lookup"><span data-stu-id="038c4-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="038c4-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="038c4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="038c4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="038c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="038c4-105">Wyodrębnia ciąg Pauli i jego qubite indeksy Pauli terminu opisanego przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="038c4-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="038c4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="038c4-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="038c4-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="038c4-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="038c4-108">`GeneratorIndex` Typ, który koduje termin Pauli.</span><span class="sxs-lookup"><span data-stu-id="038c4-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="038c4-109">Output: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="038c4-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="038c4-110">Pauli ciąg terminu opisanego przez `GeneratorIndex` , i indeksów do qubits, na którym działa.</span><span class="sxs-lookup"><span data-stu-id="038c4-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>