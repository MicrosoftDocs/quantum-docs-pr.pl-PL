---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713594"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="991a5-102">BoolArrayAsResultArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="991a5-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="991a5-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="991a5-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="991a5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="991a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="991a5-105">Konwertuje `Bool[]` Typ na `Result[]` Typ, gdzie `true` jest mapowany na `One` i `false` jest mapowany na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="991a5-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="991a5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="991a5-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="991a5-107">Wejście: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="991a5-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="991a5-108">`Bool[]` do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="991a5-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="991a5-109">Dane wyjściowe __: <Result> nieprawidłowe__ []</span><span class="sxs-lookup"><span data-stu-id="991a5-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="991a5-110">`Result[]`Reprezentujący `input` .</span><span class="sxs-lookup"><span data-stu-id="991a5-110">A `Result[]` representing the `input`.</span></span>