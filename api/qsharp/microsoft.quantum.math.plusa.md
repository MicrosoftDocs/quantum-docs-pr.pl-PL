---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194835"
---
# <a name="plusa-function"></a><span data-ttu-id="f628b-102">Plusa — funkcja</span><span class="sxs-lookup"><span data-stu-id="f628b-102">PlusA function</span></span>

<span data-ttu-id="f628b-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f628b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f628b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f628b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f628b-105">Zwraca sumę (konkatenację) dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="f628b-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="f628b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f628b-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="f628b-107">a: "element []</span><span class="sxs-lookup"><span data-stu-id="f628b-107">a : 'Element[]</span></span>

<span data-ttu-id="f628b-108">Pierwsze dane wejściowe $a $ mają być sumowane.</span><span class="sxs-lookup"><span data-stu-id="f628b-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="f628b-109">b: "element []</span><span class="sxs-lookup"><span data-stu-id="f628b-109">b : 'Element[]</span></span>

<span data-ttu-id="f628b-110">Druga wartość wejściowa $b $ do sumowania.</span><span class="sxs-lookup"><span data-stu-id="f628b-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="f628b-111">Output: "element []</span><span class="sxs-lookup"><span data-stu-id="f628b-111">Output : 'Element[]</span></span>

<span data-ttu-id="f628b-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="f628b-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f628b-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f628b-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="f628b-114">"Element</span><span class="sxs-lookup"><span data-stu-id="f628b-114">'Element</span></span>

<span data-ttu-id="f628b-115">Typ każdego elementu w każdej z dwóch tablic wejściowych.</span><span class="sxs-lookup"><span data-stu-id="f628b-115">The type of each element in each of the two input arrays.</span></span>