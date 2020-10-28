---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716968"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="b0b69-102">ApplyToTailC, operacja</span><span class="sxs-lookup"><span data-stu-id="b0b69-102">ApplyToTailC operation</span></span>

<span data-ttu-id="b0b69-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0b69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0b69-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0b69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0b69-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b0b69-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b0b69-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b0b69-106">Description</span></span>

<span data-ttu-id="b0b69-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b0b69-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b0b69-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b0b69-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="b0b69-109">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0b69-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b0b69-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b0b69-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b0b69-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="b0b69-111">targets : 'T[]</span></span>

<span data-ttu-id="b0b69-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="b0b69-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0b69-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0b69-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0b69-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b0b69-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0b69-115">'C</span><span class="sxs-lookup"><span data-stu-id="b0b69-115">'T</span></span>

<span data-ttu-id="b0b69-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b0b69-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0b69-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0b69-117">See Also</span></span>

- [<span data-ttu-id="b0b69-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="b0b69-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="b0b69-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="b0b69-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="b0b69-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b0b69-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)