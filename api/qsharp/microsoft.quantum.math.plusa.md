---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709604"
---
# <a name="plusa-function"></a><span data-ttu-id="5b31a-102">Plusa — funkcja</span><span class="sxs-lookup"><span data-stu-id="5b31a-102">PlusA function</span></span>

<span data-ttu-id="5b31a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5b31a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5b31a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b31a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b31a-105">Zwraca sumę (konkatenację) dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="5b31a-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="5b31a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5b31a-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="5b31a-107">a: "element []</span><span class="sxs-lookup"><span data-stu-id="5b31a-107">a : 'Element[]</span></span>

<span data-ttu-id="5b31a-108">Pierwsze dane wejściowe $a $ mają być sumowane.</span><span class="sxs-lookup"><span data-stu-id="5b31a-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="5b31a-109">b: "element []</span><span class="sxs-lookup"><span data-stu-id="5b31a-109">b : 'Element[]</span></span>

<span data-ttu-id="5b31a-110">Druga wartość wejściowa $b $ do sumowania.</span><span class="sxs-lookup"><span data-stu-id="5b31a-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="5b31a-111">Output: "element []</span><span class="sxs-lookup"><span data-stu-id="5b31a-111">Output : 'Element[]</span></span>

<span data-ttu-id="5b31a-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="5b31a-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5b31a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5b31a-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="5b31a-114">"Element</span><span class="sxs-lookup"><span data-stu-id="5b31a-114">'Element</span></span>

<span data-ttu-id="5b31a-115">Typ każdego elementu w każdej z dwóch tablic wejściowych.</span><span class="sxs-lookup"><span data-stu-id="5b31a-115">The type of each element in each of the two input arrays.</span></span>