---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712777"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="3812c-102">EqualityFactB, funkcja</span><span class="sxs-lookup"><span data-stu-id="3812c-102">EqualityFactB function</span></span>

<span data-ttu-id="3812c-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3812c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3812c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3812c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3812c-105">Potwierdza, że klasyczna zmienna logiczna ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="3812c-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3812c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3812c-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="3812c-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3812c-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3812c-108">Zmienna, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="3812c-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="3812c-109">Oczekiwano: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3812c-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3812c-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="3812c-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="3812c-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3812c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3812c-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="3812c-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3812c-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3812c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

