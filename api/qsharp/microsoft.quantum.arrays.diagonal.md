---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkcja ukośna
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719385"
---
# <a name="diagonal-function"></a><span data-ttu-id="a621a-102">Funkcja ukośna</span><span class="sxs-lookup"><span data-stu-id="a621a-102">Diagonal function</span></span>

<span data-ttu-id="a621a-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a621a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a621a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a621a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a621a-105">Zwraca tablicę elementów ukośnych macierzy 2-wymiarowej.</span><span class="sxs-lookup"><span data-stu-id="a621a-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a621a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a621a-106">Description</span></span>

<span data-ttu-id="a621a-107">Jeśli Dwuwymiarowa tablica nie ma kształtu kwadratowego, zostanie zwrócony ukośnie na minimum względem liczby wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="a621a-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="a621a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a621a-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="a621a-109">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="a621a-109">matrix : 'T[][]</span></span>

<span data-ttu-id="a621a-110">Macierz 2-wymiarową w kolejności wierszy</span><span class="sxs-lookup"><span data-stu-id="a621a-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="a621a-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="a621a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a621a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a621a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a621a-113">'C</span><span class="sxs-lookup"><span data-stu-id="a621a-113">'T</span></span>

<span data-ttu-id="a621a-114">Typ każdego elementu `matrix` .</span><span class="sxs-lookup"><span data-stu-id="a621a-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a621a-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a621a-115">See Also</span></span>

- [<span data-ttu-id="a621a-116">Microsoft. Quantum. Arrays. transponowanych</span><span class="sxs-lookup"><span data-stu-id="a621a-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)