---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841333"
---
# <a name="applytohead-operation"></a><span data-ttu-id="4277f-102">ApplyToHead, operacja</span><span class="sxs-lookup"><span data-stu-id="4277f-102">ApplyToHead operation</span></span>

<span data-ttu-id="4277f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4277f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4277f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4277f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4277f-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="4277f-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4277f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4277f-106">Description</span></span>

<span data-ttu-id="4277f-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4277f-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4277f-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4277f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4277f-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4277f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4277f-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4277f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4277f-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="4277f-111">targets : 'T[]</span></span>

<span data-ttu-id="4277f-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="4277f-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4277f-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4277f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4277f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4277f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4277f-115">'C</span><span class="sxs-lookup"><span data-stu-id="4277f-115">'T</span></span>

<span data-ttu-id="4277f-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4277f-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="4277f-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="4277f-117">Example</span></span>

<span data-ttu-id="4277f-118">Następujące fragmenty kodu Q # są równoważne:</span><span class="sxs-lookup"><span data-stu-id="4277f-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="4277f-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4277f-119">See Also</span></span>

- [<span data-ttu-id="4277f-120">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="4277f-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="4277f-121">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="4277f-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4277f-122">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="4277f-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)