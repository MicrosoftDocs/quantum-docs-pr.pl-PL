---
uid: Microsoft.Quantum.Arrays.Flattened
title: Spłaszczona funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848617"
---
# <a name="flattened-function"></a><span data-ttu-id="e09ef-102">Spłaszczona funkcja</span><span class="sxs-lookup"><span data-stu-id="e09ef-102">Flattened function</span></span>

<span data-ttu-id="e09ef-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e09ef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e09ef-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e09ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e09ef-105">Dana tablica tablic zwraca połączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="e09ef-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e09ef-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e09ef-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="e09ef-107">Tablice: t [] []</span><span class="sxs-lookup"><span data-stu-id="e09ef-107">arrays : 'T[][]</span></span>

<span data-ttu-id="e09ef-108">Tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="e09ef-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="e09ef-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="e09ef-109">Output : 'T[]</span></span>

<span data-ttu-id="e09ef-110">Łączenie wszystkich tablic.</span><span class="sxs-lookup"><span data-stu-id="e09ef-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e09ef-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e09ef-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e09ef-112">'C</span><span class="sxs-lookup"><span data-stu-id="e09ef-112">'T</span></span>

<span data-ttu-id="e09ef-113">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="e09ef-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="e09ef-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="e09ef-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```