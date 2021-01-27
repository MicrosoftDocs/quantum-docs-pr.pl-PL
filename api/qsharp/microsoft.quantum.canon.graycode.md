---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840495"
---
# <a name="graycode-function"></a><span data-ttu-id="7efbc-102">GrayCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="7efbc-102">GrayCode function</span></span>

<span data-ttu-id="7efbc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7efbc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7efbc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7efbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7efbc-105">Tworzy szare sekwencje kodu</span><span class="sxs-lookup"><span data-stu-id="7efbc-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="7efbc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7efbc-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="7efbc-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7efbc-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7efbc-108">Liczba bitów</span><span class="sxs-lookup"><span data-stu-id="7efbc-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="7efbc-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7efbc-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="7efbc-110">Tablica krotek.</span><span class="sxs-lookup"><span data-stu-id="7efbc-110">Array of tuples.</span></span> <span data-ttu-id="7efbc-111">Pierwsza wartość w spójnej kolekcji to wartość w sekwencji GrayCode drugiej wartości w spójnej lokalizacji, aby można ją było zmienić w bieżącej wartości.</span><span class="sxs-lookup"><span data-stu-id="7efbc-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="7efbc-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="7efbc-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```