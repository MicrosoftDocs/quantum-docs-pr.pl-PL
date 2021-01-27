---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkcja ukośna
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842826"
---
# <a name="diagonal-function"></a><span data-ttu-id="e4b32-102">Funkcja ukośna</span><span class="sxs-lookup"><span data-stu-id="e4b32-102">Diagonal function</span></span>

<span data-ttu-id="e4b32-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e4b32-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e4b32-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4b32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4b32-105">Zwraca tablicę elementów ukośnych macierzy 2-wymiarowej.</span><span class="sxs-lookup"><span data-stu-id="e4b32-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="e4b32-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e4b32-106">Description</span></span>

<span data-ttu-id="e4b32-107">Jeśli Dwuwymiarowa tablica nie ma kształtu kwadratowego, zostanie zwrócony ukośnie na minimum względem liczby wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="e4b32-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="e4b32-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e4b32-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="e4b32-109">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="e4b32-109">matrix : 'T[][]</span></span>

<span data-ttu-id="e4b32-110">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="e4b32-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="e4b32-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="e4b32-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e4b32-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e4b32-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4b32-113">'C</span><span class="sxs-lookup"><span data-stu-id="e4b32-113">'T</span></span>

<span data-ttu-id="e4b32-114">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="e4b32-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="e4b32-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="e4b32-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="e4b32-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e4b32-116">See Also</span></span>

- [<span data-ttu-id="e4b32-117">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="e4b32-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)