---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846178"
---
# <a name="emptyarray-function"></a><span data-ttu-id="c3276-102">EmptyArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="c3276-102">EmptyArray function</span></span>

<span data-ttu-id="c3276-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3276-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3276-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c3276-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c3276-105">Zwraca pustą tablicę danego typu.</span><span class="sxs-lookup"><span data-stu-id="c3276-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="c3276-106">Dane wyjściowe: "TEle []</span><span class="sxs-lookup"><span data-stu-id="c3276-106">Output : 'TElement[]</span></span>

<span data-ttu-id="c3276-107">Pusta tablica.</span><span class="sxs-lookup"><span data-stu-id="c3276-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3276-108">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c3276-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="c3276-109">"TEle</span><span class="sxs-lookup"><span data-stu-id="c3276-109">'TElement</span></span>

<span data-ttu-id="c3276-110">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="c3276-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="c3276-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="c3276-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```