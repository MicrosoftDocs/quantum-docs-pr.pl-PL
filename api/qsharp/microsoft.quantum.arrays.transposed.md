---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponowano funkcję
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219995"
---
# <a name="transposed-function"></a><span data-ttu-id="4f7fd-102">Transponowano funkcję</span><span class="sxs-lookup"><span data-stu-id="4f7fd-102">Transposed function</span></span>

<span data-ttu-id="4f7fd-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4f7fd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4f7fd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f7fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f7fd-105">Zwraca transpozycję macierzy reprezentowanej jako tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="4f7fd-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="4f7fd-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4f7fd-106">Description</span></span>

<span data-ttu-id="4f7fd-107">Dane wejściowe jako $r \times c $ z $r $ wierszy i $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="4f7fd-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="4f7fd-108">Macierz jest oparta na wierszach, tj., `matrix[i][j]` uzyskuje dostęp do elementu w wierszu $i $ i column $j $.</span><span class="sxs-lookup"><span data-stu-id="4f7fd-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="4f7fd-109">Ta funkcja zwraca $c \times r $ Matrix, która jest transponowaną macierzy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="4f7fd-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="4f7fd-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4f7fd-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="4f7fd-111">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="4f7fd-111">matrix : 'T[][]</span></span>

<span data-ttu-id="4f7fd-112">Oparta na wierszach $r \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="4f7fd-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="4f7fd-113">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="4f7fd-113">Output : 'T[][]</span></span>

<span data-ttu-id="4f7fd-114">Transponowano $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="4f7fd-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4f7fd-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4f7fd-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f7fd-116">'C</span><span class="sxs-lookup"><span data-stu-id="4f7fd-116">'T</span></span>

<span data-ttu-id="4f7fd-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="4f7fd-117">The type of each element of `matrix`.</span></span>