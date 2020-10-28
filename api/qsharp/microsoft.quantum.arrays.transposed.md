---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponowano funkcję
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718812"
---
# <a name="transposed-function"></a><span data-ttu-id="cea5c-102">Transponowano funkcję</span><span class="sxs-lookup"><span data-stu-id="cea5c-102">Transposed function</span></span>

<span data-ttu-id="cea5c-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cea5c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cea5c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cea5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cea5c-105">Zwraca transpozycję macierzy reprezentowanej jako tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="cea5c-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="cea5c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cea5c-106">Description</span></span>

<span data-ttu-id="cea5c-107">Dane wejściowe jako $r \times c $ z $r $ wierszy i $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="cea5c-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="cea5c-108">Macierz jest oparta na wierszach, tj., `matrix[i][j]` uzyskuje dostęp do elementu w wierszu $i $ i column $j $.</span><span class="sxs-lookup"><span data-stu-id="cea5c-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="cea5c-109">Ta funkcja zwraca $c \times r $ Matrix, która jest transponowaną macierzy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="cea5c-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="cea5c-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cea5c-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="cea5c-111">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="cea5c-111">matrix : 'T[][]</span></span>

<span data-ttu-id="cea5c-112">Oparta na wierszach $r \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="cea5c-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="cea5c-113">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="cea5c-113">Output : 'T[][]</span></span>

<span data-ttu-id="cea5c-114">Transponowano $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="cea5c-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cea5c-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cea5c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cea5c-116">'C</span><span class="sxs-lookup"><span data-stu-id="cea5c-116">'T</span></span>

<span data-ttu-id="cea5c-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="cea5c-117">The type of each element of `matrix`.</span></span>