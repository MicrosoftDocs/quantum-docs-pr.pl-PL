---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224466"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="7d31f-102">BoolArrayAsResultArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="7d31f-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="7d31f-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="7d31f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="7d31f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d31f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d31f-105">Konwertuje `Bool[]` Typ na `Result[]` Typ, gdzie `true` jest mapowany na `One` i `false` jest mapowany na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7d31f-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="7d31f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7d31f-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="7d31f-107">Wejście: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7d31f-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7d31f-108">`Bool[]` do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="7d31f-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7d31f-109">Dane wyjściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="7d31f-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="7d31f-110">`Result[]`Reprezentujący `input` .</span><span class="sxs-lookup"><span data-stu-id="7d31f-110">A `Result[]` representing the `input`.</span></span>