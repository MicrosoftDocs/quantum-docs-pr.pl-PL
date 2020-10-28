---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719448"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="56669-102">ColumnAtUnchecked, funkcja</span><span class="sxs-lookup"><span data-stu-id="56669-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="56669-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="56669-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="56669-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56669-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56669-105">Ta funkcja nie sprawdza dla kształtu macierzy</span><span class="sxs-lookup"><span data-stu-id="56669-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="56669-106">Opis</span><span class="sxs-lookup"><span data-stu-id="56669-106">Description</span></span>

<span data-ttu-id="56669-107">Ta funkcja może być używana w innych funkcjach wielowymiarowych, które już sprawdzają macierz wejściową dla prawidłowego prostokątnego kształtu.</span><span class="sxs-lookup"><span data-stu-id="56669-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="56669-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="56669-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="56669-109">kolumna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56669-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="56669-110">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="56669-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="56669-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="56669-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56669-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="56669-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56669-113">'C</span><span class="sxs-lookup"><span data-stu-id="56669-113">'T</span></span>

