---
uid: Microsoft.Quantum.Arrays.Head
title: Funkcja główna
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848571"
---
# <a name="head-function"></a><span data-ttu-id="b5e27-102">Funkcja główna</span><span class="sxs-lookup"><span data-stu-id="b5e27-102">Head function</span></span>

<span data-ttu-id="b5e27-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5e27-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5e27-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5e27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5e27-105">Zwraca pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5e27-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="b5e27-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5e27-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="b5e27-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="b5e27-107">array : 'A[]</span></span>

<span data-ttu-id="b5e27-108">Tablica, z której jest pobierany pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="b5e27-108">Array of which the first element is taken.</span></span> <span data-ttu-id="b5e27-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="b5e27-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="b5e27-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="b5e27-110">Output : 'A</span></span>

<span data-ttu-id="b5e27-111">Pierwszy element tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5e27-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5e27-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5e27-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="b5e27-113">"A</span><span class="sxs-lookup"><span data-stu-id="b5e27-113">'A</span></span>

<span data-ttu-id="b5e27-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5e27-114">The type of the array elements.</span></span>