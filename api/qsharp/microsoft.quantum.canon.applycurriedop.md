---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841932"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="6a0e4-102">ApplyCurriedOp, operacja</span><span class="sxs-lookup"><span data-stu-id="6a0e4-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="6a0e4-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a0e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a0e4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a0e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="6a0e4-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6a0e4-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="6a0e4-106">curriedOp: t-> ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="6a0e4-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="6a0e4-107">pierwszy: 'T</span><span class="sxs-lookup"><span data-stu-id="6a0e4-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="6a0e4-108">sekundę: ' U</span><span class="sxs-lookup"><span data-stu-id="6a0e4-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6a0e4-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a0e4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a0e4-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6a0e4-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a0e4-111">'C</span><span class="sxs-lookup"><span data-stu-id="6a0e4-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="6a0e4-112">' U</span><span class="sxs-lookup"><span data-stu-id="6a0e4-112">'U</span></span>

