---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850821"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="3a971-102">ApplyToEachIndexC, operacja</span><span class="sxs-lookup"><span data-stu-id="3a971-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="3a971-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a971-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a971-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a971-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="3a971-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="3a971-106">Modyfikator `C` wskazuje, że operacje pojedynczej qubit są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="3a971-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3a971-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3a971-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="3a971-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="3a971-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3a971-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="3a971-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3a971-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="3a971-110">register : 'T[]</span></span>

<span data-ttu-id="3a971-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="3a971-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a971-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a971-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3a971-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3a971-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3a971-114">'C</span><span class="sxs-lookup"><span data-stu-id="3a971-114">'T</span></span>

<span data-ttu-id="3a971-115">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="3a971-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a971-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a971-116">See Also</span></span>

- [<span data-ttu-id="3a971-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="3a971-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)