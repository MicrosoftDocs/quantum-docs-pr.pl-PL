---
uid: Microsoft.Quantum.Bitwise.And
title: And — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842162"
---
# <a name="and-function"></a><span data-ttu-id="a071a-102">And — funkcja</span><span class="sxs-lookup"><span data-stu-id="a071a-102">And function</span></span>

<span data-ttu-id="a071a-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="a071a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="a071a-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a071a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a071a-105">Zwraca wartości bitowe i z dwóch liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="a071a-105">Returns the bitwise AND of two integers.</span></span>
<span data-ttu-id="a071a-106">Wykonuje to takie samo obliczenie jak wbudowany `&&&` operator.</span><span class="sxs-lookup"><span data-stu-id="a071a-106">This performs the same computation as the built-in `&&&` operator.</span></span>

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a071a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a071a-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a071a-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a071a-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="a071a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a071a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="a071a-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a071a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="a071a-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="a071a-111">Example</span></span>

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a><span data-ttu-id="a071a-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a071a-112">Remarks</span></span>

<span data-ttu-id="a071a-113">Aby uzyskać więcej informacji, zobacz [ &amp; operator języka C#](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binarny).</span><span class="sxs-lookup"><span data-stu-id="a071a-113">See the [C# &amp; Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binary) for more details.</span></span>