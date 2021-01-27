---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 67491c3302392e9793677727606df1baaf4f205a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852368"
---
# <a name="operationpowa-function"></a><span data-ttu-id="577b9-102">OperationPowA, funkcja</span><span class="sxs-lookup"><span data-stu-id="577b9-102">OperationPowA function</span></span>

<span data-ttu-id="577b9-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="577b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="577b9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="577b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="577b9-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="577b9-105">Raises an operation to a power.</span></span>
<span data-ttu-id="577b9-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="577b9-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="577b9-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="577b9-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="577b9-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="577b9-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="577b9-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="577b9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="577b9-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="577b9-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="577b9-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="577b9-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="577b9-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="577b9-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="577b9-113">Wartość wyjściowa: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="577b9-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="577b9-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="577b9-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="577b9-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="577b9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="577b9-116">'C</span><span class="sxs-lookup"><span data-stu-id="577b9-116">'T</span></span>

<span data-ttu-id="577b9-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="577b9-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="577b9-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="577b9-118">See Also</span></span>

- [<span data-ttu-id="577b9-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="577b9-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)