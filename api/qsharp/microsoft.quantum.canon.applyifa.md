---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718248"
---
# <a name="applyifa-operation"></a><span data-ttu-id="54977-102">ApplyIfA, operacja</span><span class="sxs-lookup"><span data-stu-id="54977-102">ApplyIfA operation</span></span>

<span data-ttu-id="54977-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54977-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54977-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54977-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54977-105">Stosuje operację przylegającej do stanu na klasycznym.</span><span class="sxs-lookup"><span data-stu-id="54977-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="54977-106">Opis</span><span class="sxs-lookup"><span data-stu-id="54977-106">Description</span></span>

<span data-ttu-id="54977-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="54977-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="54977-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="54977-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="54977-109">Sufiks `A` wskazuje, że operacja, która ma zostać zastosowana, to przylegający.</span><span class="sxs-lookup"><span data-stu-id="54977-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="54977-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="54977-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="54977-111">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54977-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="54977-112">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="54977-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="54977-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54977-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54977-114">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="54977-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="54977-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="54977-115">target : 'T</span></span>

<span data-ttu-id="54977-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="54977-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54977-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54977-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54977-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="54977-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54977-119">'C</span><span class="sxs-lookup"><span data-stu-id="54977-119">'T</span></span>

<span data-ttu-id="54977-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="54977-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="54977-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54977-121">See Also</span></span>

- [<span data-ttu-id="54977-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="54977-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="54977-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="54977-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="54977-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="54977-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)