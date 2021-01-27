---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852305"
---
# <a name="operationpowca-function"></a><span data-ttu-id="f82ea-102">OperationPowCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="f82ea-102">OperationPowCA function</span></span>

<span data-ttu-id="f82ea-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f82ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f82ea-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f82ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f82ea-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="f82ea-105">Raises an operation to a power.</span></span>
<span data-ttu-id="f82ea-106">Modyfikator `A` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="f82ea-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="f82ea-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="f82ea-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="f82ea-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f82ea-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="f82ea-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="f82ea-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f82ea-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="f82ea-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f82ea-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f82ea-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f82ea-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="f82ea-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="f82ea-113">Wynik: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="f82ea-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f82ea-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="f82ea-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f82ea-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f82ea-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f82ea-116">'C</span><span class="sxs-lookup"><span data-stu-id="f82ea-116">'T</span></span>

<span data-ttu-id="f82ea-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="f82ea-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="f82ea-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f82ea-118">See Also</span></span>

- [<span data-ttu-id="f82ea-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="f82ea-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)