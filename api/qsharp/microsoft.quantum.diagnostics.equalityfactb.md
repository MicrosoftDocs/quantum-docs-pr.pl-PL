---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829203"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="8f928-102">EqualityFactB, funkcja</span><span class="sxs-lookup"><span data-stu-id="8f928-102">EqualityFactB function</span></span>

<span data-ttu-id="8f928-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8f928-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8f928-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f928-105">Potwierdza, że klasyczna zmienna logiczna ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="8f928-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8f928-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f928-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="8f928-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f928-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f928-108">Zmienna, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="8f928-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="8f928-109">Oczekiwano: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f928-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f928-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="8f928-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="8f928-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8f928-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8f928-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="8f928-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f928-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f928-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

