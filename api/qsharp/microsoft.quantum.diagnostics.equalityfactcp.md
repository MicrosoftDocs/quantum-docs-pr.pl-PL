---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201856"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="f4539-102">EqualityFactCP, funkcja</span><span class="sxs-lookup"><span data-stu-id="f4539-102">EqualityFactCP function</span></span>

<span data-ttu-id="f4539-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f4539-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f4539-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4539-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4539-105">Potwierdza, że liczba złożona ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="f4539-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f4539-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f4539-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="f4539-107">rzeczywista: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f4539-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f4539-108">Wartość, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="f4539-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="f4539-109">Oczekiwano: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f4539-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f4539-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="f4539-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="f4539-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f4539-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f4539-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="f4539-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4539-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4539-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

