---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkcja prefiksów
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220396"
---
# <a name="prefixes-function"></a><span data-ttu-id="9cf7d-102">Funkcja prefiksów</span><span class="sxs-lookup"><span data-stu-id="9cf7d-102">Prefixes function</span></span>

<span data-ttu-id="9cf7d-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9cf7d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9cf7d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9cf7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9cf7d-105">Podaną tablicę zwraca wszystkie jej prefiksy.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="9cf7d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf7d-106">Description</span></span>

<span data-ttu-id="9cf7d-107">Zwraca tablicę wszystkich prefiksów, rozpoczynając od tablicy, która ma tylko pierwszy element do momentu ukończenia kompletnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="9cf7d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9cf7d-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9cf7d-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="9cf7d-109">array : 'T[]</span></span>

<span data-ttu-id="9cf7d-110">Tablica elementów.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="9cf7d-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="9cf7d-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9cf7d-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9cf7d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9cf7d-113">'C</span><span class="sxs-lookup"><span data-stu-id="9cf7d-113">'T</span></span>

<span data-ttu-id="9cf7d-114">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-114">The type of `array` elements.</span></span>