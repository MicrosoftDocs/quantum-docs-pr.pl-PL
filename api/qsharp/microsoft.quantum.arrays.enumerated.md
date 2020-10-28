---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkcja wyliczana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719304"
---
# <a name="enumerated-function"></a><span data-ttu-id="06aec-102">Funkcja wyliczana</span><span class="sxs-lookup"><span data-stu-id="06aec-102">Enumerated function</span></span>

<span data-ttu-id="06aec-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="06aec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="06aec-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06aec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06aec-105">Dana tablica zwraca nową tablicę zawierającą elementy oryginalnej tablicy wraz z indeksami każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="06aec-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="06aec-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="06aec-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="06aec-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="06aec-107">array : 'TElement[]</span></span>

<span data-ttu-id="06aec-108">Tablica, której elementy mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="06aec-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="06aec-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int), "tele") []</span><span class="sxs-lookup"><span data-stu-id="06aec-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="06aec-110">Nowa tablica zawierająca elementy oryginalnej tablicy wraz z ich indeksami.</span><span class="sxs-lookup"><span data-stu-id="06aec-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06aec-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="06aec-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="06aec-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="06aec-112">'TElement</span></span>

<span data-ttu-id="06aec-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="06aec-113">The type of elements of the array.</span></span>