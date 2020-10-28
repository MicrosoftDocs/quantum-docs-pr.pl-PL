---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715717"
---
# <a name="operationpowa-function"></a><span data-ttu-id="4dc75-102">OperationPowA, funkcja</span><span class="sxs-lookup"><span data-stu-id="4dc75-102">OperationPowA function</span></span>

<span data-ttu-id="4dc75-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dc75-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dc75-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dc75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dc75-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="4dc75-105">Raises an operation to a power.</span></span>
<span data-ttu-id="4dc75-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="4dc75-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="4dc75-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="4dc75-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="4dc75-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4dc75-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="4dc75-109">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dc75-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4dc75-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="4dc75-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="4dc75-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4dc75-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4dc75-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="4dc75-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="4dc75-113">Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dc75-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4dc75-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="4dc75-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4dc75-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4dc75-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dc75-116">'C</span><span class="sxs-lookup"><span data-stu-id="4dc75-116">'T</span></span>

<span data-ttu-id="4dc75-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="4dc75-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dc75-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4dc75-118">See Also</span></span>

- [<span data-ttu-id="4dc75-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="4dc75-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)