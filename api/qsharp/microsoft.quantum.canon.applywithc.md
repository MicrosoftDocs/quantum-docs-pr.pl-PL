---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 393db9f8ce092100abc157ace1ee9fbbb3b06d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850387"
---
# <a name="applywithc-operation"></a><span data-ttu-id="ee6c5-102">ApplyWithC, operacja</span><span class="sxs-lookup"><span data-stu-id="ee6c5-102">ApplyWithC operation</span></span>

<span data-ttu-id="ee6c5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee6c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee6c5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee6c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee6c5-105">Dwie operacje mają zastosowanie jeden, jak jest sprzężony z drugim.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="ee6c5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ee6c5-106">Description</span></span>

<span data-ttu-id="ee6c5-107">Dwie operacje opisane odpowiednio przez operatory jednostkowe $U $ i $V $, stosują je w sekwencji $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="ee6c5-108">Oznacza to, że ta operacja implementuje operator jednostki dostarczone przez $V $ sprzężone z $U $.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="ee6c5-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ee6c5-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="ee6c5-110">outerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="ee6c5-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ee6c5-111">Operacja $U $, która powinna być używana do sprzężonia $V $.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="ee6c5-112">Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="ee6c5-113">innerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="ee6c5-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ee6c5-114">Operacja $V $ jest sprzężona.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="ee6c5-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="ee6c5-115">target : 'T</span></span>

<span data-ttu-id="ee6c5-116">Dane wejściowe, które mają zostać przekazane do operacji zewnętrznych i wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee6c5-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee6c5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee6c5-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ee6c5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee6c5-119">'C</span><span class="sxs-lookup"><span data-stu-id="ee6c5-119">'T</span></span>

<span data-ttu-id="ee6c5-120">Obiekt docelowy, na którym działa każda z operacji wewnętrznych i zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee6c5-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee6c5-121">Remarks</span></span>

<span data-ttu-id="ee6c5-122">Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.</span><span class="sxs-lookup"><span data-stu-id="ee6c5-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee6c5-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee6c5-123">See Also</span></span>

- [<span data-ttu-id="ee6c5-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="ee6c5-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="ee6c5-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="ee6c5-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="ee6c5-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="ee6c5-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)