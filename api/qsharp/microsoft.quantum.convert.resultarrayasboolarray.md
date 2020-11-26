---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224228"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="d1bd7-102">ResultArrayAsBoolArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="d1bd7-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="d1bd7-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d1bd7-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d1bd7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1bd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1bd7-105">Konwertuje `Result[]` Typ na `Bool[]` Typ, gdzie `One` jest mapowany na `true` i `Zero` jest mapowany na `false` .</span><span class="sxs-lookup"><span data-stu-id="d1bd7-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="d1bd7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d1bd7-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="d1bd7-107">dane wejściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="d1bd7-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="d1bd7-108">`Result[]` do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d1bd7-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d1bd7-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d1bd7-110">`Bool[]`Reprezentujący `input` .</span><span class="sxs-lookup"><span data-stu-id="d1bd7-110">A `Bool[]` representing the `input`.</span></span>