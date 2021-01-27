---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844624"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="601ca-102">ApplyToEach, operacja</span><span class="sxs-lookup"><span data-stu-id="601ca-102">ApplyToEach operation</span></span>

<span data-ttu-id="601ca-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="601ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="601ca-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="601ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="601ca-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="601ca-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="601ca-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="601ca-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="601ca-107">singleElementOperation: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="601ca-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="601ca-108">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="601ca-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="601ca-109">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="601ca-109">register : 'T[]</span></span>

<span data-ttu-id="601ca-110">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="601ca-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="601ca-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="601ca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="601ca-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="601ca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="601ca-113">'C</span><span class="sxs-lookup"><span data-stu-id="601ca-113">'T</span></span>

<span data-ttu-id="601ca-114">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="601ca-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="601ca-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="601ca-115">Example</span></span>

<span data-ttu-id="601ca-116">Przygotuj stan qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="601ca-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="601ca-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="601ca-117">See Also</span></span>

- [<span data-ttu-id="601ca-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="601ca-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="601ca-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="601ca-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="601ca-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="601ca-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)