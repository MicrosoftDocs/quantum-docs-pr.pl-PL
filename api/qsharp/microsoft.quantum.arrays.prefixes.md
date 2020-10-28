---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkcja prefiksów
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718941"
---
# <a name="prefixes-function"></a><span data-ttu-id="def55-102">Funkcja prefiksów</span><span class="sxs-lookup"><span data-stu-id="def55-102">Prefixes function</span></span>

<span data-ttu-id="def55-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="def55-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="def55-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="def55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="def55-105">Podaną tablicę zwraca wszystkie jej prefiksy.</span><span class="sxs-lookup"><span data-stu-id="def55-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="def55-106">Opis</span><span class="sxs-lookup"><span data-stu-id="def55-106">Description</span></span>

<span data-ttu-id="def55-107">Zwraca tablicę wszystkich prefiksów, rozpoczynając od tablicy, która ma tylko pierwszy element do momentu ukończenia kompletnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="def55-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="def55-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="def55-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="def55-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="def55-109">array : 'T[]</span></span>

<span data-ttu-id="def55-110">Tablica elementów.</span><span class="sxs-lookup"><span data-stu-id="def55-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="def55-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="def55-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="def55-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="def55-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="def55-113">'C</span><span class="sxs-lookup"><span data-stu-id="def55-113">'T</span></span>

<span data-ttu-id="def55-114">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="def55-114">The type of `array` elements.</span></span>