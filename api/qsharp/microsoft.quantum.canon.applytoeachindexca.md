---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717514"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="a5ed4-102">ApplyToEachIndexCA, operacja</span><span class="sxs-lookup"><span data-stu-id="a5ed4-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="a5ed4-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5ed4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5ed4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5ed4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5ed4-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="a5ed4-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="a5ed4-106">Modyfikator `CA` wskazuje, że operacja pojedynczego qubit jest sąsiednia i kontrolowany.</span><span class="sxs-lookup"><span data-stu-id="a5ed4-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5ed4-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a5ed4-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="a5ed4-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="a5ed4-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a5ed4-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="a5ed4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a5ed4-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="a5ed4-110">register : 'T[]</span></span>

<span data-ttu-id="a5ed4-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="a5ed4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5ed4-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5ed4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a5ed4-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a5ed4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5ed4-114">'C</span><span class="sxs-lookup"><span data-stu-id="a5ed4-114">'T</span></span>

<span data-ttu-id="a5ed4-115">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="a5ed4-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5ed4-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5ed4-116">See Also</span></span>

- [<span data-ttu-id="a5ed4-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="a5ed4-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)