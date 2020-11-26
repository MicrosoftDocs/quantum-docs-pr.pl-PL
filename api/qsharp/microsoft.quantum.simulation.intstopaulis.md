---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230535"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="ff1a2-102">IntsToPaulis, funkcja</span><span class="sxs-lookup"><span data-stu-id="ff1a2-102">IntsToPaulis function</span></span>

<span data-ttu-id="ff1a2-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ff1a2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ff1a2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff1a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff1a2-105">Konwertuje tablicę liczb całkowitych na tablicę operatorów Pauli pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="ff1a2-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="ff1a2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ff1a2-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="ff1a2-107">liczby całkowite: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ff1a2-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ff1a2-108">Tablica liczb całkowitych w zakresie, `0..3`  który ma zostać przekonwertowany na operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="ff1a2-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="ff1a2-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ff1a2-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ff1a2-110">Tablica `paulis` operatorów Pauli o takiej `Pauli[]` samej długości jak `ints` taka, która `paulis[idxPauli]` jest równa elementowi `[PauliI, PauliX, PauliY, PauliZ]` danego elementu `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="ff1a2-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>