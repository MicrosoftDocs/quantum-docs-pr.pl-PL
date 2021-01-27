---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 141c42d335add85103e16598264f781f32ab80fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840847"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="5c4b2-102">ConjugatedByA, funkcja</span><span class="sxs-lookup"><span data-stu-id="5c4b2-102">ConjugatedByA function</span></span>

<span data-ttu-id="5c4b2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5c4b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5c4b2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c4b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c4b2-105">Dana operacja zewnętrzna i wewnętrzna zwraca nową operację, która jest sprzężona z operacją wewnętrzną przez operację zewnętrzną.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="5c4b2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5c4b2-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="5c4b2-107">outerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="5c4b2-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5c4b2-108">Operacja $U $, która powinna być używana do sprzężonia $V $.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="5c4b2-109">Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="5c4b2-110">innerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="5c4b2-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5c4b2-111">Operacja $V $ jest sprzężona.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="5c4b2-112">Wartość wyjściowa: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="5c4b2-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5c4b2-113">Nowa operacja, której akcja jest reprezentowana przez jednostkę $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5c4b2-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5c4b2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c4b2-115">'C</span><span class="sxs-lookup"><span data-stu-id="5c4b2-115">'T</span></span>

<span data-ttu-id="5c4b2-116">Typ elementu docelowego, na którym działa każda z wewnętrznych i zewnętrznych operacji.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c4b2-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c4b2-117">Remarks</span></span>

<span data-ttu-id="5c4b2-118">Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.</span><span class="sxs-lookup"><span data-stu-id="5c4b2-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c4b2-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c4b2-119">See Also</span></span>

- [<span data-ttu-id="5c4b2-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="5c4b2-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="5c4b2-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="5c4b2-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="5c4b2-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="5c4b2-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="5c4b2-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="5c4b2-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)