---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852377"
---
# <a name="operationpow-function"></a><span data-ttu-id="438af-102">OperationPow, funkcja</span><span class="sxs-lookup"><span data-stu-id="438af-102">OperationPow function</span></span>

<span data-ttu-id="438af-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="438af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="438af-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="438af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="438af-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="438af-105">Raises an operation to a power.</span></span>

<span data-ttu-id="438af-106">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="438af-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="438af-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="438af-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="438af-108">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="438af-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="438af-109">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="438af-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="438af-110">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="438af-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="438af-111">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="438af-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="438af-112">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="438af-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="438af-113">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="438af-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="438af-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="438af-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="438af-115">'C</span><span class="sxs-lookup"><span data-stu-id="438af-115">'T</span></span>

<span data-ttu-id="438af-116">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="438af-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="438af-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="438af-117">See Also</span></span>

- [<span data-ttu-id="438af-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="438af-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="438af-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="438af-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="438af-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="438af-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)