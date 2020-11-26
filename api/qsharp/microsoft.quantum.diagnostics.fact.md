---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funkcja faktów
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201686"
---
# <a name="fact-function"></a><span data-ttu-id="60ffa-102">Funkcja faktów</span><span class="sxs-lookup"><span data-stu-id="60ffa-102">Fact function</span></span>

<span data-ttu-id="60ffa-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="60ffa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="60ffa-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="60ffa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="60ffa-105">Deklaruje, że klasyczny warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="60ffa-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="60ffa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="60ffa-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="60ffa-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60ffa-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60ffa-108">Warunek, który ma zostać zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="60ffa-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="60ffa-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="60ffa-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="60ffa-110">Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="60ffa-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60ffa-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60ffa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="60ffa-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="60ffa-112">See Also</span></span>

- [<span data-ttu-id="60ffa-113">Microsoft. Quantum. Diagnostics. dosprzeczność</span><span class="sxs-lookup"><span data-stu-id="60ffa-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)