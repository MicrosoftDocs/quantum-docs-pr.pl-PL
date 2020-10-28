---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720276"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="74c86-102">DrawRandomBool, operacja</span><span class="sxs-lookup"><span data-stu-id="74c86-102">DrawRandomBool operation</span></span>

<span data-ttu-id="74c86-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="74c86-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="74c86-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74c86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74c86-105">W wyniku prawdopodobieństwa sukcesu funkcja zwraca pojedynczą wersję próbną Bernoulliego, która ma wartość true z danym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="74c86-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="74c86-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="74c86-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="74c86-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="74c86-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="74c86-108">Prawdopodobieństwo, z którym `true` należy zwrócić.</span><span class="sxs-lookup"><span data-stu-id="74c86-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="74c86-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="74c86-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="74c86-110">`true` z prawdopodobieństwem `successProbability` i `false` z prawdopodobieństwem `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="74c86-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>