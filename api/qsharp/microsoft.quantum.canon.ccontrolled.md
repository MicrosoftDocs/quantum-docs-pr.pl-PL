---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716590"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="76838-102">CControlled, funkcja</span><span class="sxs-lookup"><span data-stu-id="76838-102">CControlled function</span></span>

<span data-ttu-id="76838-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76838-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76838-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76838-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76838-105">Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="76838-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="76838-106">Jeśli `false` nie, nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="76838-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="76838-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="76838-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="76838-108">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="76838-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="76838-109">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="76838-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="76838-110">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="76838-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="76838-111">Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="76838-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76838-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="76838-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76838-113">'C</span><span class="sxs-lookup"><span data-stu-id="76838-113">'T</span></span>

<span data-ttu-id="76838-114">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="76838-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="76838-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="76838-115">See Also</span></span>

- [<span data-ttu-id="76838-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="76838-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="76838-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="76838-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="76838-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="76838-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)