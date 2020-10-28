---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716165"
---
# <a name="graycode-function"></a><span data-ttu-id="858da-102">GrayCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="858da-102">GrayCode function</span></span>

<span data-ttu-id="858da-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="858da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="858da-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="858da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="858da-105">Tworzy szare sekwencje kodu</span><span class="sxs-lookup"><span data-stu-id="858da-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="858da-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="858da-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="858da-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="858da-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="858da-108">Liczba bitów</span><span class="sxs-lookup"><span data-stu-id="858da-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="858da-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="858da-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="858da-110">Tablica krotek.</span><span class="sxs-lookup"><span data-stu-id="858da-110">Array of tuples.</span></span> <span data-ttu-id="858da-111">Pierwsza wartość w spójnej kolekcji to wartość w sekwencji GrayCode drugiej wartości w spójnej lokalizacji, aby można ją było zmienić w bieżącej wartości.</span><span class="sxs-lookup"><span data-stu-id="858da-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>