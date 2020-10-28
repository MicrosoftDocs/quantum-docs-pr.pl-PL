---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717542"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="be738-102">ApplyToEachIndex, operacja</span><span class="sxs-lookup"><span data-stu-id="be738-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="be738-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be738-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be738-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be738-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be738-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="be738-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="be738-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="be738-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="be738-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="be738-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be738-108">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="be738-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="be738-109">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="be738-109">register : 'T[]</span></span>

<span data-ttu-id="be738-110">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="be738-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be738-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be738-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be738-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="be738-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be738-113">'C</span><span class="sxs-lookup"><span data-stu-id="be738-113">'T</span></span>

<span data-ttu-id="be738-114">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="be738-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="be738-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="be738-115">See Also</span></span>

- [<span data-ttu-id="be738-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="be738-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="be738-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="be738-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="be738-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="be738-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="be738-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="be738-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)