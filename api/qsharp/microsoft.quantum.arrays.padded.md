---
uid: Microsoft.Quantum.Arrays.Padded
title: Funkcja uzupełniona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845559"
---
# <a name="padded-function"></a><span data-ttu-id="48d66-102">Funkcja uzupełniona</span><span class="sxs-lookup"><span data-stu-id="48d66-102">Padded function</span></span>

<span data-ttu-id="48d66-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48d66-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48d66-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48d66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48d66-105">Zwraca tablicę uzupełnioną o określone wartości do określonej długości.</span><span class="sxs-lookup"><span data-stu-id="48d66-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="48d66-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="48d66-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="48d66-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48d66-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48d66-108">Długość zapełnionej tablicy.</span><span class="sxs-lookup"><span data-stu-id="48d66-108">The length of the padded array.</span></span> <span data-ttu-id="48d66-109">Jeśli jest to pozytywne, `inputArray` dopełniane na końcu.</span><span class="sxs-lookup"><span data-stu-id="48d66-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="48d66-110">Jeśli jest to wartość ujemna, `inputArray` zostanie uzupełniona na ogon.</span><span class="sxs-lookup"><span data-stu-id="48d66-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="48d66-111">defaultelement: 'T</span><span class="sxs-lookup"><span data-stu-id="48d66-111">defaultElement : 'T</span></span>

<span data-ttu-id="48d66-112">Wartość domyślna służąca do uzupełniania elementów.</span><span class="sxs-lookup"><span data-stu-id="48d66-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="48d66-113">inputArray: t []</span><span class="sxs-lookup"><span data-stu-id="48d66-113">inputArray : 'T[]</span></span>

<span data-ttu-id="48d66-114">Tablica, której wartości znajdują się na początku tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="48d66-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="48d66-115">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="48d66-115">Output : 'T[]</span></span>

<span data-ttu-id="48d66-116">Tablica `output` , która jest `inputArray` uzupełniona względem elementu `defaultElement` s do `output` długości `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="48d66-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48d66-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="48d66-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48d66-118">'C</span><span class="sxs-lookup"><span data-stu-id="48d66-118">'T</span></span>

<span data-ttu-id="48d66-119">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="48d66-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="48d66-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="48d66-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```