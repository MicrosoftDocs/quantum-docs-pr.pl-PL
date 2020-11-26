---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208310"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="3cd06-102">ApplyToRestA, operacja</span><span class="sxs-lookup"><span data-stu-id="3cd06-102">ApplyToRestA operation</span></span>

<span data-ttu-id="3cd06-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3cd06-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3cd06-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3cd06-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3cd06-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="3cd06-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3cd06-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3cd06-106">Description</span></span>

<span data-ttu-id="3cd06-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="3cd06-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="3cd06-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3cd06-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3cd06-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą</span><span class="sxs-lookup"><span data-stu-id="3cd06-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3cd06-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="3cd06-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="3cd06-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="3cd06-111">targets : 'T[]</span></span>

<span data-ttu-id="3cd06-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="3cd06-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3cd06-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3cd06-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3cd06-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3cd06-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3cd06-115">'C</span><span class="sxs-lookup"><span data-stu-id="3cd06-115">'T</span></span>

<span data-ttu-id="3cd06-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="3cd06-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cd06-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3cd06-117">See Also</span></span>

- [<span data-ttu-id="3cd06-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="3cd06-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="3cd06-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="3cd06-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="3cd06-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="3cd06-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)