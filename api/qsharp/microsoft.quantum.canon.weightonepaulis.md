---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204542"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="4865f-102">WeightOnePaulis, funkcja</span><span class="sxs-lookup"><span data-stu-id="4865f-102">WeightOnePaulis function</span></span>

<span data-ttu-id="4865f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4865f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4865f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4865f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4865f-105">Zwraca tablicę wszystkich operatorów Pauli wagi 1 w danej liczbie qubits.</span><span class="sxs-lookup"><span data-stu-id="4865f-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="4865f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4865f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4865f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4865f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4865f-108">Liczba qubits, na których zdefiniowano zwrócone operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="4865f-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4865f-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4865f-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4865f-110">Tablica operatorów wieloqubitowych Pauli, z których każdy jest reprezentowany jako tablica o długości `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="4865f-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>