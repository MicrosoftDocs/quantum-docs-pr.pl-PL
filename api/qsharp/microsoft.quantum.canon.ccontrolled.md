---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841011"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="c264b-102">CControlled, funkcja</span><span class="sxs-lookup"><span data-stu-id="c264b-102">CControlled function</span></span>

<span data-ttu-id="c264b-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c264b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c264b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c264b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c264b-105">Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="c264b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="c264b-106">Jeśli `false` nie, nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="c264b-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="c264b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c264b-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="c264b-108">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="c264b-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c264b-109">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="c264b-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="c264b-110">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="c264b-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c264b-111">Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="c264b-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c264b-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c264b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c264b-113">'C</span><span class="sxs-lookup"><span data-stu-id="c264b-113">'T</span></span>

<span data-ttu-id="c264b-114">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="c264b-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c264b-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c264b-115">See Also</span></span>

- [<span data-ttu-id="c264b-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="c264b-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="c264b-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="c264b-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="c264b-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="c264b-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)