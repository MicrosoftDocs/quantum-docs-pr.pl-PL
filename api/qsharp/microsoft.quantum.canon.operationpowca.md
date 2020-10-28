---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715675"
---
# <a name="operationpowca-function"></a><span data-ttu-id="00374-102">OperationPowCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="00374-102">OperationPowCA function</span></span>

<span data-ttu-id="00374-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00374-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00374-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00374-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00374-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="00374-105">Raises an operation to a power.</span></span>
<span data-ttu-id="00374-106">Modyfikator `A` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="00374-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="00374-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="00374-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="00374-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="00374-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="00374-109">op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="00374-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="00374-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="00374-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="00374-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00374-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00374-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="00374-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="00374-113">Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + korekta</span><span class="sxs-lookup"><span data-stu-id="00374-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="00374-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="00374-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00374-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="00374-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00374-116">'C</span><span class="sxs-lookup"><span data-stu-id="00374-116">'T</span></span>

<span data-ttu-id="00374-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="00374-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="00374-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="00374-118">See Also</span></span>

- [<span data-ttu-id="00374-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="00374-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)