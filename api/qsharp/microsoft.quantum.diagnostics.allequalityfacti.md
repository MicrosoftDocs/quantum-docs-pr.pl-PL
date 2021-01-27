---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830888"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="edd33-102">AllEqualityFactI, funkcja</span><span class="sxs-lookup"><span data-stu-id="edd33-102">AllEqualityFactI function</span></span>

<span data-ttu-id="edd33-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="edd33-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="edd33-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edd33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edd33-105">Potwierdza, że dwie tablice wartości całkowitych są równe.</span><span class="sxs-lookup"><span data-stu-id="edd33-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="edd33-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="edd33-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="edd33-107">rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="edd33-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="edd33-108">Tablica, która jest generowana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="edd33-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="edd33-109">Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="edd33-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="edd33-110">Tablica, która jest oczekiwana z przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="edd33-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="edd33-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="edd33-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="edd33-112">Komunikat do wydrukowania, jeśli tablice nie są równe.</span><span class="sxs-lookup"><span data-stu-id="edd33-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="edd33-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="edd33-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

