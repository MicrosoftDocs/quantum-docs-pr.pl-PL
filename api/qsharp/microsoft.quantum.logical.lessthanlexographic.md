---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709963"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="04d28-102">LessThanLexographic, funkcja</span><span class="sxs-lookup"><span data-stu-id="04d28-102">LessThanLexographic function</span></span>

<span data-ttu-id="04d28-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="04d28-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="04d28-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04d28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04d28-105">Używane do wdrożenia `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="04d28-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="04d28-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04d28-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="04d28-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="04d28-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="04d28-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="04d28-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="04d28-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="04d28-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="04d28-110">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="04d28-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="04d28-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="04d28-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04d28-112">'C</span><span class="sxs-lookup"><span data-stu-id="04d28-112">'T</span></span>

