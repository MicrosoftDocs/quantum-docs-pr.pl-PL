---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719457"
---
# <a name="columnat-function"></a><span data-ttu-id="dc78d-102">ColumnAt, funkcja</span><span class="sxs-lookup"><span data-stu-id="dc78d-102">ColumnAt function</span></span>

<span data-ttu-id="dc78d-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dc78d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dc78d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc78d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc78d-105">Wyodrębnia kolumnę z macierzy.</span><span class="sxs-lookup"><span data-stu-id="dc78d-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="dc78d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="dc78d-106">Description</span></span>

<span data-ttu-id="dc78d-107">Ta funkcja wyodrębnia kolumnę w macierzy w kolejności wierszy.</span><span class="sxs-lookup"><span data-stu-id="dc78d-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="dc78d-108">Wyodrębnienie wiersza corrsponds do dostępu do elementu pierwszego indeksu i w związku z tym nie wymaga dalszej obróbki.</span><span class="sxs-lookup"><span data-stu-id="dc78d-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="dc78d-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dc78d-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="dc78d-110">kolumna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc78d-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc78d-111">Kolumna macierzy</span><span class="sxs-lookup"><span data-stu-id="dc78d-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="dc78d-112">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="dc78d-112">matrix : 'T[][]</span></span>

<span data-ttu-id="dc78d-113">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="dc78d-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="dc78d-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="dc78d-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc78d-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dc78d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc78d-116">'C</span><span class="sxs-lookup"><span data-stu-id="dc78d-116">'T</span></span>

<span data-ttu-id="dc78d-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="dc78d-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc78d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dc78d-118">See Also</span></span>

- [<span data-ttu-id="dc78d-119">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="dc78d-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="dc78d-120">Microsoft. Quantum. Arrays. ukośny</span><span class="sxs-lookup"><span data-stu-id="dc78d-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)