---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712782"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="b2086-102">EqualityFactC, funkcja</span><span class="sxs-lookup"><span data-stu-id="b2086-102">EqualityFactC function</span></span>

<span data-ttu-id="b2086-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b2086-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b2086-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2086-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2086-105">Potwierdza, że liczba złożona ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="b2086-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b2086-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b2086-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="b2086-107">rzeczywista: [złożona](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b2086-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b2086-108">Wartość, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="b2086-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="b2086-109">oczekiwane: [złożone](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b2086-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b2086-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="b2086-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b2086-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b2086-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b2086-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="b2086-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2086-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2086-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

