---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712768"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="97e9e-102">EqualityFactCP, funkcja</span><span class="sxs-lookup"><span data-stu-id="97e9e-102">EqualityFactCP function</span></span>

<span data-ttu-id="97e9e-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="97e9e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="97e9e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97e9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97e9e-105">Potwierdza, że liczba złożona ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="97e9e-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="97e9e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="97e9e-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="97e9e-107">rzeczywista: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="97e9e-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="97e9e-108">Wartość, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="97e9e-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="97e9e-109">Oczekiwano: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="97e9e-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="97e9e-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="97e9e-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="97e9e-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="97e9e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="97e9e-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="97e9e-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97e9e-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97e9e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

