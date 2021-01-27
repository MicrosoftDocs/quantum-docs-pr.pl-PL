---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponowano funkcję
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850934"
---
# <a name="transposed-function"></a><span data-ttu-id="f79a4-102">Transponowano funkcję</span><span class="sxs-lookup"><span data-stu-id="f79a4-102">Transposed function</span></span>

<span data-ttu-id="f79a4-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f79a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f79a4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f79a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f79a4-105">Zwraca transpozycję macierzy reprezentowanej jako tablica tablic.</span><span class="sxs-lookup"><span data-stu-id="f79a4-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="f79a4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f79a4-106">Description</span></span>

<span data-ttu-id="f79a4-107">Dane wejściowe jako $r \times c $ z $r $ wierszy i $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="f79a4-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="f79a4-108">Macierz jest oparta na wierszach, tj., `matrix[i][j]` uzyskuje dostęp do elementu w wierszu $i $ i column $j $.</span><span class="sxs-lookup"><span data-stu-id="f79a4-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="f79a4-109">Ta funkcja zwraca $c \times r $ Matrix, która jest transponowaną macierzy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="f79a4-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="f79a4-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f79a4-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="f79a4-111">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="f79a4-111">matrix : 'T[][]</span></span>

<span data-ttu-id="f79a4-112">Oparta na wierszach $r \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="f79a4-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="f79a4-113">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="f79a4-113">Output : 'T[][]</span></span>

<span data-ttu-id="f79a4-114">Transponowano $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="f79a4-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f79a4-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f79a4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f79a4-116">'C</span><span class="sxs-lookup"><span data-stu-id="f79a4-116">'T</span></span>

<span data-ttu-id="f79a4-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="f79a4-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="f79a4-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="f79a4-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```