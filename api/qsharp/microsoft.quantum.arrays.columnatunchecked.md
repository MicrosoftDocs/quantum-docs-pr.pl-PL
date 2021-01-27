---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842856"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="988ec-102">ColumnAtUnchecked, funkcja</span><span class="sxs-lookup"><span data-stu-id="988ec-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="988ec-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="988ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="988ec-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="988ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="988ec-105">Ta funkcja nie sprawdza dla kształtu macierzy</span><span class="sxs-lookup"><span data-stu-id="988ec-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="988ec-106">Opis</span><span class="sxs-lookup"><span data-stu-id="988ec-106">Description</span></span>

<span data-ttu-id="988ec-107">Ta funkcja może być używana w innych funkcjach wielowymiarowych, które już sprawdzają macierz wejściową dla prawidłowego prostokątnego kształtu.</span><span class="sxs-lookup"><span data-stu-id="988ec-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="988ec-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="988ec-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="988ec-109">kolumna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="988ec-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="988ec-110">Macierz: t [] []</span><span class="sxs-lookup"><span data-stu-id="988ec-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="988ec-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="988ec-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="988ec-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="988ec-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="988ec-113">'C</span><span class="sxs-lookup"><span data-stu-id="988ec-113">'T</span></span>

