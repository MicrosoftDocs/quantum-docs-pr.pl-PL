---
uid: Microsoft.Quantum.Arrays.Head
title: Funkcja główna
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719184"
---
# <a name="head-function"></a><span data-ttu-id="d731c-102">Funkcja główna</span><span class="sxs-lookup"><span data-stu-id="d731c-102">Head function</span></span>

<span data-ttu-id="d731c-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d731c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d731c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d731c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d731c-105">Zwraca pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="d731c-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="d731c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d731c-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="d731c-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="d731c-107">array : 'A[]</span></span>

<span data-ttu-id="d731c-108">Tablica, z której jest pobierany pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="d731c-108">Array of which the first element is taken.</span></span> <span data-ttu-id="d731c-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="d731c-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="d731c-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="d731c-110">Output : 'A</span></span>

<span data-ttu-id="d731c-111">Pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="d731c-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d731c-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d731c-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="d731c-113">"A</span><span class="sxs-lookup"><span data-stu-id="d731c-113">'A</span></span>

<span data-ttu-id="d731c-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="d731c-114">The type of the array elements.</span></span>