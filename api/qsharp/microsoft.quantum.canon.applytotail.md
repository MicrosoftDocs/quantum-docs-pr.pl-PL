---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850434"
---
# <a name="applytotail-operation"></a><span data-ttu-id="b95a7-102">ApplyToTail, operacja</span><span class="sxs-lookup"><span data-stu-id="b95a7-102">ApplyToTail operation</span></span>

<span data-ttu-id="b95a7-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b95a7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b95a7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b95a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b95a7-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b95a7-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b95a7-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b95a7-106">Description</span></span>

<span data-ttu-id="b95a7-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b95a7-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b95a7-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b95a7-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="b95a7-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b95a7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b95a7-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b95a7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b95a7-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="b95a7-111">targets : 'T[]</span></span>

<span data-ttu-id="b95a7-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="b95a7-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b95a7-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b95a7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b95a7-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b95a7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b95a7-115">'C</span><span class="sxs-lookup"><span data-stu-id="b95a7-115">'T</span></span>

<span data-ttu-id="b95a7-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b95a7-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="b95a7-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="b95a7-117">Example</span></span>

<span data-ttu-id="b95a7-118">Następujące fragmenty kodu Q # są równoważne:</span><span class="sxs-lookup"><span data-stu-id="b95a7-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="b95a7-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b95a7-119">See Also</span></span>

- [<span data-ttu-id="b95a7-120">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="b95a7-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="b95a7-121">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="b95a7-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="b95a7-122">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b95a7-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)