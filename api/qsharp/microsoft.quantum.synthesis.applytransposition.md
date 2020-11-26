---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203318"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="90d09-102">ApplyTransposition, operacja</span><span class="sxs-lookup"><span data-stu-id="90d09-102">ApplyTransposition operation</span></span>

<span data-ttu-id="90d09-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="90d09-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="90d09-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90d09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="90d09-105">Opis</span><span class="sxs-lookup"><span data-stu-id="90d09-105">Description</span></span>

<span data-ttu-id="90d09-106">Ta operacja zamienia amplitudę na indeks `a` z amplitudą przy indeksie `b` w danym stanie-Vector o `register` długości $n $.</span><span class="sxs-lookup"><span data-stu-id="90d09-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="90d09-107">Jeśli `a` jest równe `b` , wektor stanu nie jest zmieniany.</span><span class="sxs-lookup"><span data-stu-id="90d09-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="90d09-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90d09-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="90d09-109">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90d09-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90d09-110">Pierwszy indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="90d09-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="90d09-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90d09-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90d09-112">Drugi indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="90d09-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="90d09-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="90d09-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="90d09-114">Lista $n $ qubits, do której zostanie zastosowana transpozycja.</span><span class="sxs-lookup"><span data-stu-id="90d09-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90d09-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90d09-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

