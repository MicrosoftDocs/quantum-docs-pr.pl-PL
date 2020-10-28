---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716571"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="675d2-102">CControlledCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="675d2-102">CControlledCA function</span></span>

<span data-ttu-id="675d2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="675d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="675d2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="675d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="675d2-105">Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="675d2-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="675d2-106">Jeśli `false` nie, nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="675d2-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="675d2-107">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="675d2-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="675d2-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="675d2-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="675d2-109">op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="675d2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="675d2-110">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="675d2-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="675d2-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + korekta</span><span class="sxs-lookup"><span data-stu-id="675d2-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="675d2-112">Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="675d2-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="675d2-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="675d2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="675d2-114">'C</span><span class="sxs-lookup"><span data-stu-id="675d2-114">'T</span></span>

<span data-ttu-id="675d2-115">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="675d2-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="675d2-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="675d2-116">See Also</span></span>

- [<span data-ttu-id="675d2-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="675d2-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)