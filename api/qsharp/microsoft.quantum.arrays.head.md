---
uid: Microsoft.Quantum.Arrays.Head
title: Funkcja główna
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221117"
---
# <a name="head-function"></a><span data-ttu-id="8911a-102">Funkcja główna</span><span class="sxs-lookup"><span data-stu-id="8911a-102">Head function</span></span>

<span data-ttu-id="8911a-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8911a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8911a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8911a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8911a-105">Zwraca pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="8911a-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="8911a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8911a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="8911a-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="8911a-107">array : 'A[]</span></span>

<span data-ttu-id="8911a-108">Tablica, z której jest pobierany pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="8911a-108">Array of which the first element is taken.</span></span> <span data-ttu-id="8911a-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="8911a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="8911a-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="8911a-110">Output : 'A</span></span>

<span data-ttu-id="8911a-111">Pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="8911a-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8911a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8911a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="8911a-113">"A</span><span class="sxs-lookup"><span data-stu-id="8911a-113">'A</span></span>

<span data-ttu-id="8911a-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="8911a-114">The type of the array elements.</span></span>