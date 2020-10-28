---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713076"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="bca40-102">AllEqualityFactB, funkcja</span><span class="sxs-lookup"><span data-stu-id="bca40-102">AllEqualityFactB function</span></span>

<span data-ttu-id="bca40-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bca40-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bca40-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bca40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bca40-105">Potwierdza, że dwie tablice wartości logicznych są równe.</span><span class="sxs-lookup"><span data-stu-id="bca40-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bca40-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bca40-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="bca40-107">rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bca40-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="bca40-108">Tablica, która jest generowana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="bca40-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="bca40-109">Oczekiwano: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bca40-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="bca40-110">Tablica, która jest oczekiwana z przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="bca40-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="bca40-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bca40-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bca40-112">Komunikat do wydrukowania, jeśli tablice nie są równe.</span><span class="sxs-lookup"><span data-stu-id="bca40-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bca40-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bca40-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

