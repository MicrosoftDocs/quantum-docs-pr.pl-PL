---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850573"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="ecc6a-102">ApplyToMostA, operacja</span><span class="sxs-lookup"><span data-stu-id="ecc6a-102">ApplyToMostA operation</span></span>

<span data-ttu-id="ecc6a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ecc6a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ecc6a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecc6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecc6a-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="ecc6a-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="ecc6a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ecc6a-106">Description</span></span>

<span data-ttu-id="ecc6a-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ecc6a-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ecc6a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ecc6a-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="ecc6a-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą</span><span class="sxs-lookup"><span data-stu-id="ecc6a-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ecc6a-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ecc6a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ecc6a-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="ecc6a-111">targets : 'T[]</span></span>

<span data-ttu-id="ecc6a-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="ecc6a-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ecc6a-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecc6a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ecc6a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ecc6a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ecc6a-115">'C</span><span class="sxs-lookup"><span data-stu-id="ecc6a-115">'T</span></span>

<span data-ttu-id="ecc6a-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ecc6a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecc6a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ecc6a-117">See Also</span></span>

- [<span data-ttu-id="ecc6a-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="ecc6a-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="ecc6a-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="ecc6a-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="ecc6a-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="ecc6a-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)