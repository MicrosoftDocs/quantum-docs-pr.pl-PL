---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716576"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="b0a24-102">CControlledC, funkcja</span><span class="sxs-lookup"><span data-stu-id="b0a24-102">CControlledC function</span></span>

<span data-ttu-id="b0a24-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0a24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0a24-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0a24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0a24-105">Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="b0a24-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="b0a24-106">Jeśli `false` nie, nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="b0a24-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="b0a24-107">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="b0a24-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b0a24-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b0a24-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="b0a24-109">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0a24-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b0a24-110">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b0a24-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="b0a24-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0a24-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b0a24-112">Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="b0a24-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0a24-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b0a24-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0a24-114">'C</span><span class="sxs-lookup"><span data-stu-id="b0a24-114">'T</span></span>

<span data-ttu-id="b0a24-115">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b0a24-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0a24-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0a24-116">See Also</span></span>

- [<span data-ttu-id="b0a24-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="b0a24-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)