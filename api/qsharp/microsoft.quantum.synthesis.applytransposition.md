---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855579"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="fa260-102">ApplyTransposition, operacja</span><span class="sxs-lookup"><span data-stu-id="fa260-102">ApplyTransposition operation</span></span>

<span data-ttu-id="fa260-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="fa260-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="fa260-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa260-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fa260-105">Opis</span><span class="sxs-lookup"><span data-stu-id="fa260-105">Description</span></span>

<span data-ttu-id="fa260-106">Ta operacja zamienia amplitudę na indeks `a` z amplitudą przy indeksie `b` w danym stanie-Vector o `register` długości $n $.</span><span class="sxs-lookup"><span data-stu-id="fa260-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="fa260-107">Jeśli `a` jest równe `b` , wektor stanu nie jest zmieniany.</span><span class="sxs-lookup"><span data-stu-id="fa260-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="fa260-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fa260-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fa260-109">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa260-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa260-110">Pierwszy indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="fa260-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="fa260-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa260-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa260-112">Drugi indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="fa260-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fa260-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fa260-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fa260-114">Lista $n $ qubits, do której zostanie zastosowana transpozycja.</span><span class="sxs-lookup"><span data-stu-id="fa260-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa260-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa260-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="fa260-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="fa260-116">Example</span></span>

<span data-ttu-id="fa260-117">Przygotuj jednolite nadpozycja numerów $ | 1 \ rangle $, $ | 2 \ rangle $ i $ | 3 \ rangle $ on 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="fa260-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```