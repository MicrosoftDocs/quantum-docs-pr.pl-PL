---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716450"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="bed1d-102">ConjugatedByCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="bed1d-102">ConjugatedByCA function</span></span>

<span data-ttu-id="bed1d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bed1d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bed1d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bed1d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bed1d-105">Dana operacja zewnętrzna i wewnętrzna zwraca nową operację, która jest sprzężona z operacją wewnętrzną przez operację zewnętrzną.</span><span class="sxs-lookup"><span data-stu-id="bed1d-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="bed1d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bed1d-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="bed1d-107">outerOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bed1d-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bed1d-108">Operacja $U $, która powinna być używana do sprzężonia $V $.</span><span class="sxs-lookup"><span data-stu-id="bed1d-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="bed1d-109">Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.</span><span class="sxs-lookup"><span data-stu-id="bed1d-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="bed1d-110">innerOperation: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="bed1d-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bed1d-111">Operacja $V $ jest sprzężona.</span><span class="sxs-lookup"><span data-stu-id="bed1d-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="bed1d-112">Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="bed1d-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bed1d-113">Nowa operacja, której akcja jest reprezentowana przez jednostkę $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="bed1d-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bed1d-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bed1d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bed1d-115">'C</span><span class="sxs-lookup"><span data-stu-id="bed1d-115">'T</span></span>

<span data-ttu-id="bed1d-116">Typ elementu docelowego, na którym działa każda z wewnętrznych i zewnętrznych operacji.</span><span class="sxs-lookup"><span data-stu-id="bed1d-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="bed1d-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bed1d-117">Remarks</span></span>

<span data-ttu-id="bed1d-118">Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.</span><span class="sxs-lookup"><span data-stu-id="bed1d-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="bed1d-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bed1d-119">See Also</span></span>

- [<span data-ttu-id="bed1d-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="bed1d-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="bed1d-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="bed1d-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="bed1d-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="bed1d-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="bed1d-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="bed1d-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)