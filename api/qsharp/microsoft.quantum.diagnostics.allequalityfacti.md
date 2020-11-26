---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223888"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="446f0-102">AllEqualityFactI, funkcja</span><span class="sxs-lookup"><span data-stu-id="446f0-102">AllEqualityFactI function</span></span>

<span data-ttu-id="446f0-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="446f0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="446f0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="446f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="446f0-105">Potwierdza, że dwie tablice wartości całkowitych są równe.</span><span class="sxs-lookup"><span data-stu-id="446f0-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="446f0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="446f0-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="446f0-107">rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="446f0-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="446f0-108">Tablica, która jest generowana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="446f0-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="446f0-109">Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="446f0-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="446f0-110">Tablica, która jest oczekiwana z przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="446f0-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="446f0-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="446f0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="446f0-112">Komunikat do wydrukowania, jeśli tablice nie są równe.</span><span class="sxs-lookup"><span data-stu-id="446f0-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="446f0-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="446f0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

