---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834188"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="ecaaf-102">BoolArrayAsResultArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="ecaaf-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="ecaaf-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ecaaf-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ecaaf-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecaaf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecaaf-105">Konwertuje `Bool[]` Typ na `Result[]` Typ, gdzie `true` jest mapowany na `One` i `false` jest mapowany na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="ecaaf-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="ecaaf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ecaaf-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="ecaaf-107">Wejście: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ecaaf-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ecaaf-108">`Bool[]` do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="ecaaf-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ecaaf-109">Dane wyjściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="ecaaf-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="ecaaf-110">`Result[]`Reprezentujący `input` .</span><span class="sxs-lookup"><span data-stu-id="ecaaf-110">A `Result[]` representing the `input`.</span></span>