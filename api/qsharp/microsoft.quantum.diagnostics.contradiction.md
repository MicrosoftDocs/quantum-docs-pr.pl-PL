---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funkcja sprzeczności
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712866"
---
# <a name="contradiction-function"></a><span data-ttu-id="90946-102">Funkcja sprzeczności</span><span class="sxs-lookup"><span data-stu-id="90946-102">Contradiction function</span></span>

<span data-ttu-id="90946-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="90946-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="90946-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90946-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90946-105">Deklaruje, że klasyczny warunek ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="90946-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="90946-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90946-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="90946-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90946-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90946-108">Warunek, który ma zostać zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="90946-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="90946-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="90946-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="90946-110">Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="90946-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90946-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90946-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="90946-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="90946-112">See Also</span></span>

- [<span data-ttu-id="90946-113">Microsoft. Quantum. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="90946-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)