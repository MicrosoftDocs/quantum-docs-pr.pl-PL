---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210103"
---
# <a name="columnat-function"></a><span data-ttu-id="1c60f-102">ColumnAt, funkcja</span><span class="sxs-lookup"><span data-stu-id="1c60f-102">ColumnAt function</span></span>

<span data-ttu-id="1c60f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1c60f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1c60f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c60f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c60f-105">Wyodrębnia kolumnę z macierzy.</span><span class="sxs-lookup"><span data-stu-id="1c60f-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="1c60f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="1c60f-106">Description</span></span>

<span data-ttu-id="1c60f-107">Ta funkcja wyodrębnia kolumnę w macierzy w kolejności wierszy.</span><span class="sxs-lookup"><span data-stu-id="1c60f-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="1c60f-108">Wyodrębnienie wiersza corrsponds do dostępu do elementu pierwszego indeksu i w związku z tym nie wymaga dalszej obróbki.</span><span class="sxs-lookup"><span data-stu-id="1c60f-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="1c60f-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1c60f-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="1c60f-110">kolumna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c60f-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c60f-111">Kolumna macierzy</span><span class="sxs-lookup"><span data-stu-id="1c60f-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="1c60f-112">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="1c60f-112">matrix : 'T[][]</span></span>

<span data-ttu-id="1c60f-113">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="1c60f-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="1c60f-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="1c60f-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c60f-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1c60f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c60f-116">'C</span><span class="sxs-lookup"><span data-stu-id="1c60f-116">'T</span></span>

<span data-ttu-id="1c60f-117">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="1c60f-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c60f-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1c60f-118">See Also</span></span>

- [<span data-ttu-id="1c60f-119">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="1c60f-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="1c60f-120">Microsoft. Quantum. Arrays. ukośny</span><span class="sxs-lookup"><span data-stu-id="1c60f-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)