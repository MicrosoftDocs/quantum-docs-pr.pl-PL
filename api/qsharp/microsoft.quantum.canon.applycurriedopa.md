---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218958"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="dc8bd-102">ApplyCurriedOpA, operacja</span><span class="sxs-lookup"><span data-stu-id="dc8bd-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="dc8bd-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc8bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc8bd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc8bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dc8bd-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dc8bd-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="dc8bd-106">curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  jest przymiotnik</span><span class="sxs-lookup"><span data-stu-id="dc8bd-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="dc8bd-107">pierwszy: 'T</span><span class="sxs-lookup"><span data-stu-id="dc8bd-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="dc8bd-108">sekundę: ' U</span><span class="sxs-lookup"><span data-stu-id="dc8bd-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="dc8bd-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc8bd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc8bd-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dc8bd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc8bd-111">'C</span><span class="sxs-lookup"><span data-stu-id="dc8bd-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="dc8bd-112">' U</span><span class="sxs-lookup"><span data-stu-id="dc8bd-112">'U</span></span>

