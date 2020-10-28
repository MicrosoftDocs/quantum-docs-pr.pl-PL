---
uid: Microsoft.Quantum.Arrays.Padded
title: Funkcja uzupełniona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718980"
---
# <a name="padded-function"></a><span data-ttu-id="e5ca1-102">Funkcja uzupełniona</span><span class="sxs-lookup"><span data-stu-id="e5ca1-102">Padded function</span></span>

<span data-ttu-id="e5ca1-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e5ca1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e5ca1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5ca1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5ca1-105">Zwraca tablicę uzupełnioną o określone wartości do określonej długości.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e5ca1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e5ca1-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="e5ca1-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5ca1-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5ca1-108">Długość zapełnionej tablicy.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-108">The length of the padded array.</span></span> <span data-ttu-id="e5ca1-109">Jeśli jest to pozytywne, `inputArray` dopełniane na końcu.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="e5ca1-110">Jeśli jest to wartość ujemna, `inputArray` zostanie uzupełniona na ogon.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="e5ca1-111">defaultelement: 'T</span><span class="sxs-lookup"><span data-stu-id="e5ca1-111">defaultElement : 'T</span></span>

<span data-ttu-id="e5ca1-112">Wartość domyślna służąca do uzupełniania elementów.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="e5ca1-113">inputArray: t []</span><span class="sxs-lookup"><span data-stu-id="e5ca1-113">inputArray : 'T[]</span></span>

<span data-ttu-id="e5ca1-114">Tablica, której wartości znajdują się na początku tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e5ca1-115">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="e5ca1-115">Output : 'T[]</span></span>

<span data-ttu-id="e5ca1-116">Tablica `output` , która jest `inputArray` uzupełniona względem elementu `defaultElement` s do `output` długości `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="e5ca1-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5ca1-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e5ca1-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5ca1-118">'C</span><span class="sxs-lookup"><span data-stu-id="e5ca1-118">'T</span></span>

<span data-ttu-id="e5ca1-119">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="e5ca1-119">The type of the array elements.</span></span>