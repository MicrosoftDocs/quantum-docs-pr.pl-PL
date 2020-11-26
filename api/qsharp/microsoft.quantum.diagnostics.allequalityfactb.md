---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213705"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="545eb-102">AllEqualityFactB, funkcja</span><span class="sxs-lookup"><span data-stu-id="545eb-102">AllEqualityFactB function</span></span>

<span data-ttu-id="545eb-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="545eb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="545eb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="545eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="545eb-105">Potwierdza, że dwie tablice wartości logicznych są równe.</span><span class="sxs-lookup"><span data-stu-id="545eb-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="545eb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="545eb-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="545eb-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="545eb-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="545eb-108">Tablica, która jest generowana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="545eb-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="545eb-109">Oczekiwano: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="545eb-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="545eb-110">Tablica, która jest oczekiwana z przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="545eb-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="545eb-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="545eb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="545eb-112">Komunikat do wydrukowania, jeśli tablice nie są równe.</span><span class="sxs-lookup"><span data-stu-id="545eb-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="545eb-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="545eb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

