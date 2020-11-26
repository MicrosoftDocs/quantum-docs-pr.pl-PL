---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkcja ukośna
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221542"
---
# <a name="diagonal-function"></a><span data-ttu-id="f9a20-102">Funkcja ukośna</span><span class="sxs-lookup"><span data-stu-id="f9a20-102">Diagonal function</span></span>

<span data-ttu-id="f9a20-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9a20-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9a20-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9a20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9a20-105">Zwraca tablicę elementów ukośnych macierzy 2-wymiarowej.</span><span class="sxs-lookup"><span data-stu-id="f9a20-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f9a20-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f9a20-106">Description</span></span>

<span data-ttu-id="f9a20-107">Jeśli Dwuwymiarowa tablica nie ma kształtu kwadratowego, zostanie zwrócony ukośnie na minimum względem liczby wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="f9a20-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="f9a20-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f9a20-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="f9a20-109">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="f9a20-109">matrix : 'T[][]</span></span>

<span data-ttu-id="f9a20-110">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="f9a20-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="f9a20-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="f9a20-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9a20-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f9a20-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9a20-113">'C</span><span class="sxs-lookup"><span data-stu-id="f9a20-113">'T</span></span>

<span data-ttu-id="f9a20-114">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="f9a20-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9a20-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9a20-115">See Also</span></span>

- [<span data-ttu-id="f9a20-116">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="f9a20-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)