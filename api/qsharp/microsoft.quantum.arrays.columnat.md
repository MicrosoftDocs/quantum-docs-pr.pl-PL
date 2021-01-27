---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846253"
---
# <a name="columnat-function"></a><span data-ttu-id="8c760-102">ColumnAt, funkcja</span><span class="sxs-lookup"><span data-stu-id="8c760-102">ColumnAt function</span></span>

<span data-ttu-id="8c760-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8c760-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8c760-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c760-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c760-105">Wyodrębnia kolumnę z macierzy.</span><span class="sxs-lookup"><span data-stu-id="8c760-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="8c760-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8c760-106">Description</span></span>

<span data-ttu-id="8c760-107">Ta funkcja wyodrębnia kolumnę w macierzy w kolejności wierszy.</span><span class="sxs-lookup"><span data-stu-id="8c760-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="8c760-108">Wyodrębnienie wiersza corrsponds do dostępu do elementu pierwszego indeksu i w związku z tym nie wymaga dalszej obróbki.</span><span class="sxs-lookup"><span data-stu-id="8c760-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="8c760-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8c760-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="8c760-110">kolumna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c760-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c760-111">Kolumna macierzy</span><span class="sxs-lookup"><span data-stu-id="8c760-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="8c760-112">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="8c760-112">matrix : 'T[][]</span></span>

<span data-ttu-id="8c760-113">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="8c760-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="8c760-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="8c760-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c760-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8c760-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c760-116">'C</span><span class="sxs-lookup"><span data-stu-id="8c760-116">'T</span></span>

<span data-ttu-id="8c760-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="8c760-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="8c760-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="8c760-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="8c760-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8c760-119">See Also</span></span>

- [<span data-ttu-id="8c760-120">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="8c760-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="8c760-121">Microsoft. Quantum. Arrays. ukośny</span><span class="sxs-lookup"><span data-stu-id="8c760-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)