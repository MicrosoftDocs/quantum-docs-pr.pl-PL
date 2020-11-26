---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201771"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="b69f7-102">EqualityFactR, funkcja</span><span class="sxs-lookup"><span data-stu-id="b69f7-102">EqualityFactR function</span></span>

<span data-ttu-id="b69f7-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b69f7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b69f7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b69f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b69f7-105">Potwierdza, że klasyczna zmienna wynikowa ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="b69f7-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b69f7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b69f7-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="b69f7-107">rzeczywiste: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="b69f7-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="b69f7-108">Zmienna, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="b69f7-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="b69f7-109">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="b69f7-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="b69f7-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="b69f7-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b69f7-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b69f7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b69f7-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="b69f7-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b69f7-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b69f7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

