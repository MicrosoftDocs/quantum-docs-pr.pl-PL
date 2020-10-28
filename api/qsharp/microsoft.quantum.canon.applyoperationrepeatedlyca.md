---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 150750cebb8072b253272df4e6ca19819640058b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717873"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="89b3e-102">ApplyOperationRepeatedlyCA, operacja</span><span class="sxs-lookup"><span data-stu-id="89b3e-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="89b3e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89b3e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89b3e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89b3e-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="89b3e-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="89b3e-105">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="89b3e-106">op: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="89b3e-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="89b3e-107">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89b3e-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="89b3e-108">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="89b3e-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="89b3e-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89b3e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="89b3e-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="89b3e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89b3e-111">'C</span><span class="sxs-lookup"><span data-stu-id="89b3e-111">'T</span></span>

