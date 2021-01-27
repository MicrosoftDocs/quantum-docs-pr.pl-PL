---
uid: Microsoft.Quantum.Bitwise.Or
title: Or — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845277"
---
# <a name="or-function"></a><span data-ttu-id="b7a56-102">Or — funkcja</span><span class="sxs-lookup"><span data-stu-id="b7a56-102">Or function</span></span>

<span data-ttu-id="b7a56-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="b7a56-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="b7a56-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b7a56-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b7a56-105">Zwraca wartości bitowe lub z dwóch liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="b7a56-105">Returns the bitwise OR of two integers.</span></span>
<span data-ttu-id="b7a56-106">Wykonuje to takie samo obliczenie jak wbudowany `|||` operator.</span><span class="sxs-lookup"><span data-stu-id="b7a56-106">This performs the same computation as the built-in `|||` operator.</span></span>

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b7a56-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b7a56-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b7a56-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7a56-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="b7a56-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7a56-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="b7a56-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7a56-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="b7a56-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="b7a56-111">Example</span></span>

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a><span data-ttu-id="b7a56-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b7a56-112">Remarks</span></span>

<span data-ttu-id="b7a56-113">Zobacz [C# | Operatora](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="b7a56-113">See the [C# | Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) for more details.</span></span>