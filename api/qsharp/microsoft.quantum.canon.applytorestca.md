---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841240"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="0bf86-102">ApplyToRestCA, operacja</span><span class="sxs-lookup"><span data-stu-id="0bf86-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="0bf86-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bf86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bf86-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bf86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bf86-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="0bf86-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0bf86-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0bf86-106">Description</span></span>

<span data-ttu-id="0bf86-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0bf86-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0bf86-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0bf86-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="0bf86-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="0bf86-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0bf86-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="0bf86-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0bf86-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="0bf86-111">targets : 'T[]</span></span>

<span data-ttu-id="0bf86-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="0bf86-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bf86-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bf86-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0bf86-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0bf86-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bf86-115">'C</span><span class="sxs-lookup"><span data-stu-id="0bf86-115">'T</span></span>

<span data-ttu-id="0bf86-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="0bf86-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bf86-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0bf86-117">See Also</span></span>

- [<span data-ttu-id="0bf86-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="0bf86-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="0bf86-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="0bf86-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="0bf86-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="0bf86-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)