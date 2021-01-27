---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853361"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="5c169-102">EqualityFactC, funkcja</span><span class="sxs-lookup"><span data-stu-id="5c169-102">EqualityFactC function</span></span>

<span data-ttu-id="5c169-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c169-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c169-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c169-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c169-105">Potwierdza, że liczba złożona ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="5c169-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5c169-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5c169-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="5c169-107">rzeczywista: [złożona](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5c169-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5c169-108">Wartość, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="5c169-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="5c169-109">oczekiwane: [złożone](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5c169-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5c169-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="5c169-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5c169-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5c169-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5c169-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="5c169-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c169-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c169-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

