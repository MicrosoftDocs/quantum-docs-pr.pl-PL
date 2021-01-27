---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855341"
---
# <a name="rmencoding-function"></a><span data-ttu-id="71cf1-102">RMEncoding, funkcja</span><span class="sxs-lookup"><span data-stu-id="71cf1-102">RMEncoding function</span></span>

<span data-ttu-id="71cf1-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="71cf1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="71cf1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71cf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71cf1-105">{-1,1} kodowanie wartości logicznej prawdy</span><span class="sxs-lookup"><span data-stu-id="71cf1-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="71cf1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="71cf1-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="71cf1-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="71cf1-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="71cf1-108">Wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="71cf1-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="71cf1-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71cf1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71cf1-110">1, jeśli `b` ma wartość false, w przeciwnym razie-1</span><span class="sxs-lookup"><span data-stu-id="71cf1-110">1, if `b` is false, otherwise -1</span></span>