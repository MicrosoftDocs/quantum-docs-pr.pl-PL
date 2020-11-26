---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 2ff13b6b3f142437c2ca7a40884ecf1a66c6a083
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209183"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="ac5be-102">ApplyOperationRepeatedlyCA, operacja</span><span class="sxs-lookup"><span data-stu-id="ac5be-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="ac5be-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac5be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac5be-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac5be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac5be-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ac5be-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ac5be-106">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="ac5be-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="ac5be-107">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac5be-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="ac5be-108">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="ac5be-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="ac5be-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac5be-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ac5be-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ac5be-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac5be-111">'C</span><span class="sxs-lookup"><span data-stu-id="ac5be-111">'T</span></span>

