---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712763"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="0f803-102">EqualityFactI, funkcja</span><span class="sxs-lookup"><span data-stu-id="0f803-102">EqualityFactI function</span></span>

<span data-ttu-id="0f803-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0f803-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0f803-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f803-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f803-105">Potwierdza, że klasyczna zmienna int ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="0f803-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="0f803-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0f803-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="0f803-107">rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f803-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f803-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="0f803-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="0f803-109">Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f803-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f803-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="0f803-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="0f803-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0f803-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0f803-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="0f803-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f803-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f803-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

