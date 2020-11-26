---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206888"
---
# <a name="graycode-function"></a><span data-ttu-id="47d5a-102">GrayCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="47d5a-102">GrayCode function</span></span>

<span data-ttu-id="47d5a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47d5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47d5a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47d5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47d5a-105">Tworzy szare sekwencje kodu</span><span class="sxs-lookup"><span data-stu-id="47d5a-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="47d5a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="47d5a-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="47d5a-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47d5a-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47d5a-108">Liczba bitów</span><span class="sxs-lookup"><span data-stu-id="47d5a-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="47d5a-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="47d5a-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="47d5a-110">Tablica krotek.</span><span class="sxs-lookup"><span data-stu-id="47d5a-110">Array of tuples.</span></span> <span data-ttu-id="47d5a-111">Pierwsza wartość w spójnej kolekcji to wartość w sekwencji GrayCode drugiej wartości w spójnej lokalizacji, aby można ją było zmienić w bieżącej wartości.</span><span class="sxs-lookup"><span data-stu-id="47d5a-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>