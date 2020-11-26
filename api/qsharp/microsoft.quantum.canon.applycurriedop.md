---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219026"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="77c00-102">ApplyCurriedOp, operacja</span><span class="sxs-lookup"><span data-stu-id="77c00-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="77c00-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77c00-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77c00-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77c00-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="77c00-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="77c00-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="77c00-106">curriedOp: t-> ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="77c00-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="77c00-107">pierwszy: 'T</span><span class="sxs-lookup"><span data-stu-id="77c00-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="77c00-108">sekundę: ' U</span><span class="sxs-lookup"><span data-stu-id="77c00-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="77c00-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77c00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77c00-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="77c00-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77c00-111">'C</span><span class="sxs-lookup"><span data-stu-id="77c00-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="77c00-112">' U</span><span class="sxs-lookup"><span data-stu-id="77c00-112">'U</span></span>

