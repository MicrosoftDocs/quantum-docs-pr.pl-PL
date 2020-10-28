---
uid: Microsoft.Quantum.Arrays.Flattened
title: Spłaszczona funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719241"
---
# <a name="flattened-function"></a><span data-ttu-id="930fc-102">Spłaszczona funkcja</span><span class="sxs-lookup"><span data-stu-id="930fc-102">Flattened function</span></span>

<span data-ttu-id="930fc-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="930fc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="930fc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="930fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="930fc-105">Dana tablica tablic zwraca połączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="930fc-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="930fc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="930fc-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="930fc-107">Tablice: t [] []</span><span class="sxs-lookup"><span data-stu-id="930fc-107">arrays : 'T[][]</span></span>

<span data-ttu-id="930fc-108">Tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="930fc-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="930fc-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="930fc-109">Output : 'T[]</span></span>

<span data-ttu-id="930fc-110">Łączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="930fc-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="930fc-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="930fc-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="930fc-112">'C</span><span class="sxs-lookup"><span data-stu-id="930fc-112">'T</span></span>

<span data-ttu-id="930fc-113">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="930fc-113">The type of `array` elements.</span></span>