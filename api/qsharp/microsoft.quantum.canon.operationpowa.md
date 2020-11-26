---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205783"
---
# <a name="operationpowa-function"></a><span data-ttu-id="84660-102">OperationPowA, funkcja</span><span class="sxs-lookup"><span data-stu-id="84660-102">OperationPowA function</span></span>

<span data-ttu-id="84660-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84660-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84660-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84660-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84660-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="84660-105">Raises an operation to a power.</span></span>
<span data-ttu-id="84660-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="84660-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="84660-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="84660-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="84660-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="84660-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="84660-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="84660-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="84660-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="84660-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="84660-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84660-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84660-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="84660-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="84660-113">Wartość wyjściowa: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="84660-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="84660-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="84660-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84660-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="84660-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84660-116">'C</span><span class="sxs-lookup"><span data-stu-id="84660-116">'T</span></span>

<span data-ttu-id="84660-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="84660-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="84660-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84660-118">See Also</span></span>

- [<span data-ttu-id="84660-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="84660-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)