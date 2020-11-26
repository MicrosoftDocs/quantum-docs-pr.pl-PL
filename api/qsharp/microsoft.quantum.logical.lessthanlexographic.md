---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197674"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="7f3ce-102">LessThanLexographic, funkcja</span><span class="sxs-lookup"><span data-stu-id="7f3ce-102">LessThanLexographic function</span></span>

<span data-ttu-id="7f3ce-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7f3ce-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7f3ce-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f3ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f3ce-105">Używane do wdrożenia `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="7f3ce-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="7f3ce-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7f3ce-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="7f3ce-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7f3ce-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="7f3ce-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="7f3ce-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="7f3ce-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="7f3ce-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="7f3ce-110">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7f3ce-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7f3ce-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7f3ce-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f3ce-112">'C</span><span class="sxs-lookup"><span data-stu-id="7f3ce-112">'T</span></span>

