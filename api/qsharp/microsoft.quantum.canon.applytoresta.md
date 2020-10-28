---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717080"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="805ec-102">ApplyToRestA, operacja</span><span class="sxs-lookup"><span data-stu-id="805ec-102">ApplyToRestA operation</span></span>

<span data-ttu-id="805ec-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="805ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="805ec-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="805ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="805ec-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="805ec-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="805ec-106">Opis</span><span class="sxs-lookup"><span data-stu-id="805ec-106">Description</span></span>

<span data-ttu-id="805ec-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="805ec-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="805ec-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="805ec-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="805ec-109">op: t [] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="805ec-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="805ec-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="805ec-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="805ec-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="805ec-111">targets : 'T[]</span></span>

<span data-ttu-id="805ec-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="805ec-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="805ec-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="805ec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="805ec-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="805ec-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="805ec-115">'C</span><span class="sxs-lookup"><span data-stu-id="805ec-115">'T</span></span>

<span data-ttu-id="805ec-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="805ec-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="805ec-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="805ec-117">See Also</span></span>

- [<span data-ttu-id="805ec-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="805ec-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="805ec-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="805ec-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="805ec-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="805ec-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)