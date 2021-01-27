---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850797"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="a2901-102">ApplyToEachIndexCA, operacja</span><span class="sxs-lookup"><span data-stu-id="a2901-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="a2901-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2901-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2901-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2901-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2901-105">Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="a2901-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="a2901-106">Modyfikator `CA` wskazuje, że operacja pojedynczego qubit jest sąsiednia i kontrolowany.</span><span class="sxs-lookup"><span data-stu-id="a2901-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a2901-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a2901-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="a2901-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="a2901-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a2901-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="a2901-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a2901-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="a2901-110">register : 'T[]</span></span>

<span data-ttu-id="a2901-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="a2901-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2901-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2901-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a2901-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a2901-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2901-114">'C</span><span class="sxs-lookup"><span data-stu-id="a2901-114">'T</span></span>

<span data-ttu-id="a2901-115">Obiekt docelowy, na którym działa każda z operacji.</span><span class="sxs-lookup"><span data-stu-id="a2901-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2901-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2901-116">See Also</span></span>

- [<span data-ttu-id="a2901-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="a2901-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)