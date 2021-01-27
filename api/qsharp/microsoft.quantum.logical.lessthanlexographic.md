---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815642"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="d2669-102">LessThanLexographic, funkcja</span><span class="sxs-lookup"><span data-stu-id="d2669-102">LessThanLexographic function</span></span>

<span data-ttu-id="d2669-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d2669-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d2669-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2669-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2669-105">Używane do wdrożenia `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="d2669-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="d2669-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d2669-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="d2669-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d2669-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="d2669-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="d2669-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="d2669-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="d2669-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="d2669-110">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d2669-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d2669-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d2669-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2669-112">'C</span><span class="sxs-lookup"><span data-stu-id="d2669-112">'T</span></span>

