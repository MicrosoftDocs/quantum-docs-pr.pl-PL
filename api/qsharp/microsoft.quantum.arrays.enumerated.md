---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkcja wyliczana
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221423"
---
# <a name="enumerated-function"></a><span data-ttu-id="c3967-102">Funkcja wyliczana</span><span class="sxs-lookup"><span data-stu-id="c3967-102">Enumerated function</span></span>

<span data-ttu-id="c3967-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3967-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3967-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3967-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3967-105">Dana tablica zwraca nową tablicę zawierającą elementy oryginalnej tablicy wraz z indeksami każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="c3967-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="c3967-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c3967-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="c3967-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="c3967-107">array : 'TElement[]</span></span>

<span data-ttu-id="c3967-108">Tablica, której elementy mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="c3967-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="c3967-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int), "tele") []</span><span class="sxs-lookup"><span data-stu-id="c3967-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="c3967-110">Nowa tablica zawierająca elementy oryginalnej tablicy wraz z ich indeksami.</span><span class="sxs-lookup"><span data-stu-id="c3967-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3967-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c3967-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="c3967-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="c3967-112">'TElement</span></span>

<span data-ttu-id="c3967-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="c3967-113">The type of elements of the array.</span></span>