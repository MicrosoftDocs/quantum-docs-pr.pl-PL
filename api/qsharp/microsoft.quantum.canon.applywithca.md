---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716884"
---
# <a name="applywithca-operation"></a><span data-ttu-id="aa031-102">ApplyWithCA, operacja</span><span class="sxs-lookup"><span data-stu-id="aa031-102">ApplyWithCA operation</span></span>

<span data-ttu-id="aa031-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa031-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa031-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa031-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa031-105">Dwie operacje mają zastosowanie jeden, jak jest sprzężony z drugim.</span><span class="sxs-lookup"><span data-stu-id="aa031-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="aa031-106">Opis</span><span class="sxs-lookup"><span data-stu-id="aa031-106">Description</span></span>

<span data-ttu-id="aa031-107">Dwie operacje opisane odpowiednio przez operatory jednostkowe $U $ i $V $, stosują je w sekwencji $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="aa031-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="aa031-108">Oznacza to, że ta operacja implementuje operator jednostki dostarczone przez $V $ sprzężone z $U $.</span><span class="sxs-lookup"><span data-stu-id="aa031-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="aa031-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa031-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="aa031-110">outerOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa031-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aa031-111">Operacja $U $, która powinna być używana do sprzężonia $V $.</span><span class="sxs-lookup"><span data-stu-id="aa031-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="aa031-112">Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.</span><span class="sxs-lookup"><span data-stu-id="aa031-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="aa031-113">innerOperation: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="aa031-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="aa031-114">Operacja $V $ jest sprzężona.</span><span class="sxs-lookup"><span data-stu-id="aa031-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="aa031-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="aa031-115">target : 'T</span></span>

<span data-ttu-id="aa031-116">Dane wejściowe, które mają zostać przekazane do operacji zewnętrznych i wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="aa031-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa031-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa031-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aa031-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aa031-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa031-119">'C</span><span class="sxs-lookup"><span data-stu-id="aa031-119">'T</span></span>

<span data-ttu-id="aa031-120">Obiekt docelowy, na którym działa każda z operacji wewnętrznych i zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="aa031-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa031-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="aa031-121">Remarks</span></span>

<span data-ttu-id="aa031-122">Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.</span><span class="sxs-lookup"><span data-stu-id="aa031-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa031-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa031-123">See Also</span></span>

- [<span data-ttu-id="aa031-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="aa031-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="aa031-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="aa031-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="aa031-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="aa031-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)