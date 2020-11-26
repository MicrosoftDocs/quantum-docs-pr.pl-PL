---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217870"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="ec3ff-102">ApplyToEach, operacja</span><span class="sxs-lookup"><span data-stu-id="ec3ff-102">ApplyToEach operation</span></span>

<span data-ttu-id="ec3ff-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec3ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec3ff-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec3ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec3ff-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ec3ff-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec3ff-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="ec3ff-107">singleElementOperation: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ec3ff-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ec3ff-108">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ec3ff-109">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="ec3ff-109">register : 'T[]</span></span>

<span data-ttu-id="ec3ff-110">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec3ff-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec3ff-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ec3ff-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ec3ff-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec3ff-113">'C</span><span class="sxs-lookup"><span data-stu-id="ec3ff-113">'T</span></span>

<span data-ttu-id="ec3ff-114">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec3ff-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec3ff-115">See Also</span></span>

- [<span data-ttu-id="ec3ff-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ec3ff-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="ec3ff-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="ec3ff-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="ec3ff-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="ec3ff-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)