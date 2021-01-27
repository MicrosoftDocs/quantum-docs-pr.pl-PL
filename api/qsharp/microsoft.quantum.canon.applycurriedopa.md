---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 100d8a42d6475d3cdda349a2e685a6fbfff23cdc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845089"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="1ee69-102">ApplyCurriedOpA, operacja</span><span class="sxs-lookup"><span data-stu-id="1ee69-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="1ee69-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ee69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ee69-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ee69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="1ee69-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1ee69-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="1ee69-106">curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  jest przymiotnik</span><span class="sxs-lookup"><span data-stu-id="1ee69-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="1ee69-107">pierwszy: 'T</span><span class="sxs-lookup"><span data-stu-id="1ee69-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="1ee69-108">sekundę: ' U</span><span class="sxs-lookup"><span data-stu-id="1ee69-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1ee69-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ee69-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1ee69-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1ee69-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ee69-111">'C</span><span class="sxs-lookup"><span data-stu-id="1ee69-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="1ee69-112">' U</span><span class="sxs-lookup"><span data-stu-id="1ee69-112">'U</span></span>

