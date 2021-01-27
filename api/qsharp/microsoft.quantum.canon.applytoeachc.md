---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850854"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="4913d-102">ApplyToEachC, operacja</span><span class="sxs-lookup"><span data-stu-id="4913d-102">ApplyToEachC operation</span></span>

<span data-ttu-id="4913d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4913d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4913d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4913d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4913d-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="4913d-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="4913d-106">Modyfikator `C` wskazuje, że operacje pojedynczej qubit są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="4913d-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="4913d-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4913d-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="4913d-108">singleElementOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="4913d-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4913d-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="4913d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="4913d-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="4913d-110">register : 'T[]</span></span>

<span data-ttu-id="4913d-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="4913d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4913d-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4913d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4913d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4913d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4913d-114">'C</span><span class="sxs-lookup"><span data-stu-id="4913d-114">'T</span></span>

<span data-ttu-id="4913d-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="4913d-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="4913d-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="4913d-116">Example</span></span>

<span data-ttu-id="4913d-117">Przygotuj stan qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="4913d-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="4913d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4913d-118">See Also</span></span>

- [<span data-ttu-id="4913d-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="4913d-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)