---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842715"
---
# <a name="plusa-function"></a><span data-ttu-id="b5b62-102">Plusa — funkcja</span><span class="sxs-lookup"><span data-stu-id="b5b62-102">PlusA function</span></span>

<span data-ttu-id="b5b62-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b5b62-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b5b62-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5b62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5b62-105">Zwraca sumę (konkatenację) dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b5b62-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="b5b62-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5b62-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="b5b62-107">a: "element []</span><span class="sxs-lookup"><span data-stu-id="b5b62-107">a : 'Element[]</span></span>

<span data-ttu-id="b5b62-108">Pierwsze dane wejściowe $a $ mają być sumowane.</span><span class="sxs-lookup"><span data-stu-id="b5b62-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="b5b62-109">b: "element []</span><span class="sxs-lookup"><span data-stu-id="b5b62-109">b : 'Element[]</span></span>

<span data-ttu-id="b5b62-110">Druga wartość wejściowa $b $ do sumowania.</span><span class="sxs-lookup"><span data-stu-id="b5b62-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="b5b62-111">Output: "element []</span><span class="sxs-lookup"><span data-stu-id="b5b62-111">Output : 'Element[]</span></span>

<span data-ttu-id="b5b62-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="b5b62-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5b62-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5b62-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="b5b62-114">"Element</span><span class="sxs-lookup"><span data-stu-id="b5b62-114">'Element</span></span>

<span data-ttu-id="b5b62-115">Typ każdego elementu w każdej z dwóch tablic wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b5b62-115">The type of each element in each of the two input arrays.</span></span>