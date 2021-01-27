---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 7af80b4f310aa6f7fbb616d8249d2b7c5a0b7edf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841630"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="b40b2-102">ApplyOperationRepeatedlyCA, operacja</span><span class="sxs-lookup"><span data-stu-id="b40b2-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="b40b2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b40b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b40b2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b40b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b40b2-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b40b2-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b40b2-106">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="b40b2-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="b40b2-107">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b40b2-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="b40b2-108">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="b40b2-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b40b2-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b40b2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b40b2-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b40b2-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b40b2-111">'C</span><span class="sxs-lookup"><span data-stu-id="b40b2-111">'T</span></span>

