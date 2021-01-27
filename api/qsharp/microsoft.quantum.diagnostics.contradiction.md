---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funkcja sprzeczności
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829362"
---
# <a name="contradiction-function"></a><span data-ttu-id="a3149-102">Funkcja sprzeczności</span><span class="sxs-lookup"><span data-stu-id="a3149-102">Contradiction function</span></span>

<span data-ttu-id="a3149-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a3149-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a3149-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a3149-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a3149-105">Deklaruje, że klasyczny warunek ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="a3149-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a3149-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a3149-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="a3149-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a3149-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a3149-108">Warunek, który ma zostać zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="a3149-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="a3149-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a3149-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a3149-110">Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="a3149-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3149-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3149-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a3149-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3149-112">Example</span></span>

<span data-ttu-id="a3149-113">Następujący kod Q # będzie drukował "Hello, World":</span><span class="sxs-lookup"><span data-stu-id="a3149-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="a3149-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3149-114">See Also</span></span>

- [<span data-ttu-id="a3149-115">Microsoft. Quantum. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="a3149-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)