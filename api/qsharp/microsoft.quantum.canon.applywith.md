---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 7127df047a260b18d75efb092e8e090e2d0b207a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850405"
---
# <a name="applywith-operation"></a><span data-ttu-id="37c1d-102">ApplyWith, operacja</span><span class="sxs-lookup"><span data-stu-id="37c1d-102">ApplyWith operation</span></span>

<span data-ttu-id="37c1d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37c1d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37c1d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37c1d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37c1d-105">Dwie operacje mają zastosowanie jeden, jak jest sprzężony z drugim.</span><span class="sxs-lookup"><span data-stu-id="37c1d-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="37c1d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="37c1d-106">Description</span></span>

<span data-ttu-id="37c1d-107">Dwie operacje opisane odpowiednio przez operatory jednostkowe $U $ i $V $, stosują je w sekwencji $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="37c1d-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="37c1d-108">Oznacza to, że ta operacja implementuje operator jednostki dostarczone przez $V $ sprzężone z $U $.</span><span class="sxs-lookup"><span data-stu-id="37c1d-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="37c1d-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="37c1d-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="37c1d-110">outerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="37c1d-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="37c1d-111">Operacja $U $, która powinna być używana do sprzężonia $V $.</span><span class="sxs-lookup"><span data-stu-id="37c1d-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="37c1d-112">Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.</span><span class="sxs-lookup"><span data-stu-id="37c1d-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="37c1d-113">innerOperation: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="37c1d-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37c1d-114">Operacja $V $ jest sprzężona.</span><span class="sxs-lookup"><span data-stu-id="37c1d-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="37c1d-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="37c1d-115">target : 'T</span></span>

<span data-ttu-id="37c1d-116">Dane wejściowe, które mają zostać przekazane do operacji zewnętrznych i wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="37c1d-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37c1d-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37c1d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37c1d-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="37c1d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37c1d-119">'C</span><span class="sxs-lookup"><span data-stu-id="37c1d-119">'T</span></span>

<span data-ttu-id="37c1d-120">Obiekt docelowy, na którym działa każda z operacji wewnętrznych i zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="37c1d-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="37c1d-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37c1d-121">Remarks</span></span>

<span data-ttu-id="37c1d-122">Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.</span><span class="sxs-lookup"><span data-stu-id="37c1d-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="37c1d-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37c1d-123">See Also</span></span>

- [<span data-ttu-id="37c1d-124">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="37c1d-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="37c1d-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="37c1d-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="37c1d-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="37c1d-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)