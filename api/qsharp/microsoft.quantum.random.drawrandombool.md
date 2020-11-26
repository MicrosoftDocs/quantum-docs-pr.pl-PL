---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192965"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="880b8-102">DrawRandomBool, operacja</span><span class="sxs-lookup"><span data-stu-id="880b8-102">DrawRandomBool operation</span></span>

<span data-ttu-id="880b8-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="880b8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="880b8-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="880b8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="880b8-105">W wyniku prawdopodobieństwa sukcesu funkcja zwraca pojedynczą wersję próbną Bernoulliego, która ma wartość true z danym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="880b8-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="880b8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="880b8-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="880b8-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="880b8-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="880b8-108">Prawdopodobieństwo, z którym `true` należy zwrócić.</span><span class="sxs-lookup"><span data-stu-id="880b8-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="880b8-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="880b8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="880b8-110">`true` z prawdopodobieństwem `successProbability` i `false` z prawdopodobieństwem `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="880b8-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>