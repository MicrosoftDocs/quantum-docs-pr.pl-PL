---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207466"
---
# <a name="composedoutput-function"></a><span data-ttu-id="ca86d-102">ComposedOutput, funkcja</span><span class="sxs-lookup"><span data-stu-id="ca86d-102">ComposedOutput function</span></span>

<span data-ttu-id="ca86d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca86d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca86d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca86d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca86d-105">Zwraca dane wyjściowe kompozycji `inner` i `outer` dla danego danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="ca86d-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="ca86d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca86d-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="ca86d-107">zewnętrzne: "U->" V</span><span class="sxs-lookup"><span data-stu-id="ca86d-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="ca86d-108">wewnętrzny: brak > ' U</span><span class="sxs-lookup"><span data-stu-id="ca86d-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="ca86d-109">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="ca86d-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="ca86d-110">Wynik: ' V</span><span class="sxs-lookup"><span data-stu-id="ca86d-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca86d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ca86d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca86d-112">'C</span><span class="sxs-lookup"><span data-stu-id="ca86d-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="ca86d-113">' U</span><span class="sxs-lookup"><span data-stu-id="ca86d-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="ca86d-114">"V</span><span class="sxs-lookup"><span data-stu-id="ca86d-114">'V</span></span>

