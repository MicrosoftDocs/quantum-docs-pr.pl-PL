---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716585"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="54124-102">CControlledA, funkcja</span><span class="sxs-lookup"><span data-stu-id="54124-102">CControlledA function</span></span>

<span data-ttu-id="54124-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54124-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54124-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54124-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54124-105">Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="54124-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="54124-106">Jeśli `false` nie, nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="54124-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="54124-107">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="54124-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="54124-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="54124-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="54124-109">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54124-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="54124-110">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="54124-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="54124-111">Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54124-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="54124-112">Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="54124-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="54124-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="54124-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54124-114">'C</span><span class="sxs-lookup"><span data-stu-id="54124-114">'T</span></span>

<span data-ttu-id="54124-115">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="54124-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="54124-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54124-116">See Also</span></span>

- [<span data-ttu-id="54124-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="54124-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)