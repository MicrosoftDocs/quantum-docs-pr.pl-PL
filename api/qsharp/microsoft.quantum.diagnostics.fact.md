---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funkcja faktów
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853320"
---
# <a name="fact-function"></a><span data-ttu-id="9e362-102">Funkcja faktów</span><span class="sxs-lookup"><span data-stu-id="9e362-102">Fact function</span></span>

<span data-ttu-id="9e362-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9e362-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9e362-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9e362-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9e362-105">Deklaruje, że klasyczny warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="9e362-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9e362-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9e362-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="9e362-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9e362-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9e362-108">Warunek, który ma zostać zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="9e362-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="9e362-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9e362-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9e362-110">Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="9e362-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e362-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e362-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="9e362-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="9e362-112">Example</span></span>

<span data-ttu-id="9e362-113">Poniższy fragment kodu Q # zakończy się niepowodzeniem:</span><span class="sxs-lookup"><span data-stu-id="9e362-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="9e362-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9e362-114">See Also</span></span>

- [<span data-ttu-id="9e362-115">Microsoft. Quantum. Diagnostics. dosprzeczność</span><span class="sxs-lookup"><span data-stu-id="9e362-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)