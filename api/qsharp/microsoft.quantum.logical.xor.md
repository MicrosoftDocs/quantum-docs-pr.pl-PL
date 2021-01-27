---
uid: Microsoft.Quantum.Logical.Xor
title: XOR — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848450"
---
# <a name="xor-function"></a><span data-ttu-id="b5bf7-102">XOR — funkcja</span><span class="sxs-lookup"><span data-stu-id="b5bf7-102">Xor function</span></span>

<span data-ttu-id="b5bf7-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b5bf7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b5bf7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5bf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5bf7-105">Zwraca wartość logiczną bez odłączenia dwóch wartości.</span><span class="sxs-lookup"><span data-stu-id="b5bf7-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="b5bf7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5bf7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="b5bf7-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5bf7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5bf7-108">Pierwsza wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="b5bf7-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="b5bf7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5bf7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5bf7-110">Druga wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="b5bf7-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b5bf7-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5bf7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5bf7-112">`true` if i tylko wtedy, gdy dokładnie jeden z `a` i `b` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="b5bf7-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>