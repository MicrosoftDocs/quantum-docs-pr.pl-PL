---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222375"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="0ce9c-102">ReflectAboutInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="0ce9c-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="0ce9c-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0ce9c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ce9c-105">Odzwierciedla rejestr Quantum o danej klasycznej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0ce9c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0ce9c-106">Description</span></span>

<span data-ttu-id="0ce9c-107">Zgodnie z wstępnym rejestrem Quantum w stanie $ \ sum_i \ alpha_i \ket{i} $, gdzie każdy $ \ket{i} $ jest stanem bazowym reprezentującym liczbę całkowitą $i $, odzwierciedla stan rejestru o stanie bazowym dla danej liczby całkowitej $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="0ce9c-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="0ce9c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0ce9c-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="0ce9c-109">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ce9c-110">Klasyczna liczba całkowita — indeksowanie stanu podstawy, które należy uwzględnić.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="0ce9c-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="0ce9c-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0ce9c-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ce9c-113">Remarks</span></span>

<span data-ttu-id="0ce9c-114">Ta operacja jest zaimplementowana w miejscu bez jawnego przydziału dodatkowych pomocniczych qubits.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>