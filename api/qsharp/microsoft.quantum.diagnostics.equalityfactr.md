---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853331"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="a8206-102">EqualityFactR, funkcja</span><span class="sxs-lookup"><span data-stu-id="a8206-102">EqualityFactR function</span></span>

<span data-ttu-id="a8206-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a8206-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a8206-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8206-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8206-105">Potwierdza, że klasyczna zmienna wynikowa ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="a8206-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a8206-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a8206-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="a8206-107">rzeczywiste: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="a8206-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="a8206-108">Zmienna, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="a8206-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="a8206-109">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="a8206-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="a8206-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="a8206-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="a8206-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a8206-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a8206-112">Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.</span><span class="sxs-lookup"><span data-stu-id="a8206-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8206-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8206-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

