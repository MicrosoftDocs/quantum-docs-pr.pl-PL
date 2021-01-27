---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850509"
---
# <a name="applytorest-operation"></a><span data-ttu-id="ac2f1-102">ApplyToRest, operacja</span><span class="sxs-lookup"><span data-stu-id="ac2f1-102">ApplyToRest operation</span></span>

<span data-ttu-id="ac2f1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac2f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac2f1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac2f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac2f1-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="ac2f1-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ac2f1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ac2f1-106">Description</span></span>

<span data-ttu-id="ac2f1-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ac2f1-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ac2f1-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ac2f1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ac2f1-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ac2f1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ac2f1-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ac2f1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ac2f1-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="ac2f1-111">targets : 'T[]</span></span>

<span data-ttu-id="ac2f1-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="ac2f1-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac2f1-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac2f1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ac2f1-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ac2f1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac2f1-115">'C</span><span class="sxs-lookup"><span data-stu-id="ac2f1-115">'T</span></span>

<span data-ttu-id="ac2f1-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ac2f1-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="ac2f1-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac2f1-117">Example</span></span>

<span data-ttu-id="ac2f1-118">Następujące fragmenty kodu Q # są równoważne:</span><span class="sxs-lookup"><span data-stu-id="ac2f1-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="ac2f1-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac2f1-119">See Also</span></span>

- [<span data-ttu-id="ac2f1-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="ac2f1-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="ac2f1-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="ac2f1-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="ac2f1-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="ac2f1-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)