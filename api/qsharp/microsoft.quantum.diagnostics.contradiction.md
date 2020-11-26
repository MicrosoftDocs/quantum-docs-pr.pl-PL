---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funkcja sprzeczności
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202145"
---
# <a name="contradiction-function"></a><span data-ttu-id="ec9c1-102">Funkcja sprzeczności</span><span class="sxs-lookup"><span data-stu-id="ec9c1-102">Contradiction function</span></span>

<span data-ttu-id="ec9c1-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ec9c1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ec9c1-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ec9c1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ec9c1-105">Deklaruje, że klasyczny warunek ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="ec9c1-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ec9c1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec9c1-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="ec9c1-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ec9c1-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ec9c1-108">Warunek, który ma zostać zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="ec9c1-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="ec9c1-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ec9c1-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ec9c1-110">Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="ec9c1-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec9c1-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec9c1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ec9c1-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec9c1-112">See Also</span></span>

- [<span data-ttu-id="ec9c1-113">Microsoft. Quantum. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="ec9c1-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)