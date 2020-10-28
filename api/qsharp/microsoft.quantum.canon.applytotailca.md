---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716940"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="9698e-102">ApplyToTailCA, operacja</span><span class="sxs-lookup"><span data-stu-id="9698e-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="9698e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9698e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9698e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9698e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9698e-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9698e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9698e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9698e-106">Description</span></span>

<span data-ttu-id="9698e-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9698e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9698e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9698e-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="9698e-109">op: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="9698e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9698e-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9698e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9698e-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="9698e-111">targets : 'T[]</span></span>

<span data-ttu-id="9698e-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="9698e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9698e-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9698e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9698e-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9698e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9698e-115">'C</span><span class="sxs-lookup"><span data-stu-id="9698e-115">'T</span></span>

<span data-ttu-id="9698e-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9698e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9698e-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9698e-117">See Also</span></span>

- [<span data-ttu-id="9698e-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="9698e-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="9698e-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="9698e-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="9698e-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="9698e-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)