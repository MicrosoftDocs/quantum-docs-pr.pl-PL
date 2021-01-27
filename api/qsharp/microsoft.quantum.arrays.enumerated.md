---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkcja wyliczana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848124"
---
# <a name="enumerated-function"></a><span data-ttu-id="a933e-102">Funkcja wyliczana</span><span class="sxs-lookup"><span data-stu-id="a933e-102">Enumerated function</span></span>

<span data-ttu-id="a933e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a933e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a933e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a933e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a933e-105">Dana tablica zwraca nową tablicę zawierającą elementy oryginalnej tablicy wraz z indeksami każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="a933e-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="a933e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a933e-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="a933e-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="a933e-107">array : 'TElement[]</span></span>

<span data-ttu-id="a933e-108">Tablica, której elementy mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="a933e-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="a933e-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int), "tele") []</span><span class="sxs-lookup"><span data-stu-id="a933e-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="a933e-110">Nowa tablica zawierająca elementy oryginalnej tablicy wraz z ich indeksami.</span><span class="sxs-lookup"><span data-stu-id="a933e-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a933e-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a933e-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="a933e-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="a933e-112">'TElement</span></span>

<span data-ttu-id="a933e-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="a933e-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="a933e-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="a933e-114">Example</span></span>

<span data-ttu-id="a933e-115">Następujące `for` pętle są równoważne:</span><span class="sxs-lookup"><span data-stu-id="a933e-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```