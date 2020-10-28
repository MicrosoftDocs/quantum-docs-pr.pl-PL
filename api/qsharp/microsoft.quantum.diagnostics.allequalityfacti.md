---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713071"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="0321d-102">AllEqualityFactI, funkcja</span><span class="sxs-lookup"><span data-stu-id="0321d-102">AllEqualityFactI function</span></span>

<span data-ttu-id="0321d-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0321d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0321d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0321d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0321d-105">Potwierdza, że dwie tablice wartości całkowitych są równe.</span><span class="sxs-lookup"><span data-stu-id="0321d-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="0321d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0321d-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="0321d-107">rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0321d-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0321d-108">Tablica, która jest generowana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="0321d-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="0321d-109">Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0321d-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0321d-110">Tablica, która jest oczekiwana z przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="0321d-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="0321d-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0321d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0321d-112">Komunikat do wydrukowania, jeśli tablice nie są równe.</span><span class="sxs-lookup"><span data-stu-id="0321d-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0321d-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0321d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

