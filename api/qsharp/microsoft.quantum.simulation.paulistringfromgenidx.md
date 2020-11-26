---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230314"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="3e9fe-102">PauliStringFromGenIdx, funkcja</span><span class="sxs-lookup"><span data-stu-id="3e9fe-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="3e9fe-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3e9fe-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3e9fe-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e9fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e9fe-105">Wyodrębnia ciąg Pauli i jego qubite indeksy Pauli terminu opisanego przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3e9fe-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="3e9fe-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3e9fe-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="3e9fe-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3e9fe-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3e9fe-108">`GeneratorIndex` Typ, który koduje termin Pauli.</span><span class="sxs-lookup"><span data-stu-id="3e9fe-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="3e9fe-109">Output: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="3e9fe-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="3e9fe-110">Pauli ciąg terminu opisanego przez `GeneratorIndex` , i indeksów do qubits, na którym działa.</span><span class="sxs-lookup"><span data-stu-id="3e9fe-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>