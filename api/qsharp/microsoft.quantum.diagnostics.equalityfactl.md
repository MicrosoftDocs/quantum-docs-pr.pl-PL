---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201805"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="57c18-102">EqualityFactL, funkcja</span><span class="sxs-lookup"><span data-stu-id="57c18-102">EqualityFactL function</span></span>

<span data-ttu-id="57c18-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="57c18-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="57c18-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57c18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57c18-105">Potwierdza, że klasyczna zmienna BigInt ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="57c18-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="57c18-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="57c18-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="57c18-107">rzeczywista: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="57c18-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="57c18-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="57c18-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="57c18-109">Oczekiwano: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="57c18-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="57c18-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="57c18-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="57c18-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="57c18-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="57c18-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="57c18-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57c18-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57c18-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

