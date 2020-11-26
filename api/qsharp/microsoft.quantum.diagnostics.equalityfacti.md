---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201839"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="e4aa1-102">EqualityFactI, funkcja</span><span class="sxs-lookup"><span data-stu-id="e4aa1-102">EqualityFactI function</span></span>

<span data-ttu-id="e4aa1-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e4aa1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4aa1-105">Potwierdza, że klasyczna zmienna int ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="e4aa1-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e4aa1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e4aa1-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="e4aa1-107">rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4aa1-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="e4aa1-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="e4aa1-109">Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4aa1-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="e4aa1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="e4aa1-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e4aa1-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="e4aa1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4aa1-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4aa1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

