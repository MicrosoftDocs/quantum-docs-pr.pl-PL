---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852349"
---
# <a name="operationpowc-function"></a><span data-ttu-id="2e514-102">OperationPowC, funkcja</span><span class="sxs-lookup"><span data-stu-id="2e514-102">OperationPowC function</span></span>

<span data-ttu-id="2e514-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e514-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e514-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e514-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e514-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="2e514-105">Raises an operation to a power.</span></span>
<span data-ttu-id="2e514-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="2e514-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="2e514-107">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="2e514-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="2e514-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2e514-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="2e514-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="2e514-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2e514-110">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="2e514-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="2e514-111">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e514-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e514-112">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="2e514-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="2e514-113">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="2e514-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2e514-114">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="2e514-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e514-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2e514-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e514-116">'C</span><span class="sxs-lookup"><span data-stu-id="2e514-116">'T</span></span>

<span data-ttu-id="2e514-117">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="2e514-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e514-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e514-118">See Also</span></span>

- [<span data-ttu-id="2e514-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="2e514-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)