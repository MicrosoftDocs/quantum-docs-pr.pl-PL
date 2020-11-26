---
uid: Microsoft.Quantum.Arrays.Flattened
title: Spłaszczona funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221219"
---
# <a name="flattened-function"></a><span data-ttu-id="d1c61-102">Spłaszczona funkcja</span><span class="sxs-lookup"><span data-stu-id="d1c61-102">Flattened function</span></span>

<span data-ttu-id="d1c61-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d1c61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d1c61-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1c61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1c61-105">Dana tablica tablic zwraca połączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="d1c61-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d1c61-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d1c61-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="d1c61-107">Tablice: t [] []</span><span class="sxs-lookup"><span data-stu-id="d1c61-107">arrays : 'T[][]</span></span>

<span data-ttu-id="d1c61-108">Tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="d1c61-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="d1c61-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="d1c61-109">Output : 'T[]</span></span>

<span data-ttu-id="d1c61-110">Łączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="d1c61-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d1c61-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d1c61-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1c61-112">'C</span><span class="sxs-lookup"><span data-stu-id="d1c61-112">'T</span></span>

<span data-ttu-id="d1c61-113">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="d1c61-113">The type of `array` elements.</span></span>