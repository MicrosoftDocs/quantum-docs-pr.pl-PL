---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829172"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="8ab45-102">EqualityFactCP, funkcja</span><span class="sxs-lookup"><span data-stu-id="8ab45-102">EqualityFactCP function</span></span>

<span data-ttu-id="8ab45-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8ab45-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8ab45-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ab45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ab45-105">Potwierdza, że liczba złożona ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="8ab45-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8ab45-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8ab45-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="8ab45-107">rzeczywista: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8ab45-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8ab45-108">Wartość, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="8ab45-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="8ab45-109">Oczekiwano: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8ab45-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8ab45-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="8ab45-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="8ab45-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8ab45-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8ab45-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="8ab45-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ab45-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ab45-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

