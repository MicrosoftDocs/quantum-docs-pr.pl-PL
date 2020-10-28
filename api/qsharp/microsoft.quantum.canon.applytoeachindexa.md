---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717537"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="65878-102">ApplyToEachIndexA, operacja</span><span class="sxs-lookup"><span data-stu-id="65878-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="65878-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65878-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65878-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65878-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65878-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="65878-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="65878-106">Modyfikator `A` wskazuje, że operacja pojedynczego qubit jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="65878-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="65878-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="65878-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="65878-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => korektę [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65878-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="65878-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="65878-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="65878-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="65878-110">register : 'T[]</span></span>

<span data-ttu-id="65878-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="65878-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65878-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65878-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65878-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="65878-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65878-114">'C</span><span class="sxs-lookup"><span data-stu-id="65878-114">'T</span></span>

<span data-ttu-id="65878-115">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="65878-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="65878-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65878-116">See Also</span></span>

- [<span data-ttu-id="65878-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="65878-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)