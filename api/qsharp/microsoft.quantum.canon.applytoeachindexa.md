---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217598"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="9bcd2-102">ApplyToEachIndexA, operacja</span><span class="sxs-lookup"><span data-stu-id="9bcd2-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="9bcd2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9bcd2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9bcd2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bcd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bcd2-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="9bcd2-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="9bcd2-106">Modyfikator `A` wskazuje, że operacja pojedynczego qubit jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="9bcd2-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9bcd2-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9bcd2-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="9bcd2-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="9bcd2-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9bcd2-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="9bcd2-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9bcd2-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="9bcd2-110">register : 'T[]</span></span>

<span data-ttu-id="9bcd2-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="9bcd2-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9bcd2-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bcd2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9bcd2-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9bcd2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9bcd2-114">'C</span><span class="sxs-lookup"><span data-stu-id="9bcd2-114">'T</span></span>

<span data-ttu-id="9bcd2-115">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="9bcd2-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bcd2-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9bcd2-116">See Also</span></span>

- [<span data-ttu-id="9bcd2-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="9bcd2-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)