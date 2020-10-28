---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715199"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="d4ddf-102">WeightOnePaulis, funkcja</span><span class="sxs-lookup"><span data-stu-id="d4ddf-102">WeightOnePaulis function</span></span>

<span data-ttu-id="d4ddf-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4ddf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4ddf-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4ddf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4ddf-105">Zwraca tablicę wszystkich operatorów Pauli wagi 1 w danej liczbie qubits.</span><span class="sxs-lookup"><span data-stu-id="d4ddf-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="d4ddf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d4ddf-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d4ddf-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4ddf-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4ddf-108">Liczba qubits, na których zdefiniowano zwrócone operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="d4ddf-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="d4ddf-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="d4ddf-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="d4ddf-110">Tablica operatorów wieloqubitowych Pauli, z których każdy jest reprezentowany jako tablica o długości `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="d4ddf-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>