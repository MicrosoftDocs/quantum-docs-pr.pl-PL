---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725260"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="77105-102">ApplyTransposition, operacja</span><span class="sxs-lookup"><span data-stu-id="77105-102">ApplyTransposition operation</span></span>

<span data-ttu-id="77105-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="77105-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="77105-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77105-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="77105-105">Opis</span><span class="sxs-lookup"><span data-stu-id="77105-105">Description</span></span>

<span data-ttu-id="77105-106">Ta operacja zamienia amplitudę na indeks `a` z amplitudą przy indeksie `b` w danym stanie-Vector o `register` długości $n $.</span><span class="sxs-lookup"><span data-stu-id="77105-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="77105-107">Jeśli `a` jest równe `b` , wektor stanu nie jest zmieniany.</span><span class="sxs-lookup"><span data-stu-id="77105-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="77105-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="77105-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="77105-109">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77105-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77105-110">Pierwszy indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="77105-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="77105-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77105-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77105-112">Drugi indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="77105-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="77105-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="77105-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="77105-114">Lista $n $ qubits, do której zostanie zastosowana transpozycja.</span><span class="sxs-lookup"><span data-stu-id="77105-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77105-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77105-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

