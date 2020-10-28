---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717593"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="788ca-102">ApplyToEach, operacja</span><span class="sxs-lookup"><span data-stu-id="788ca-102">ApplyToEach operation</span></span>

<span data-ttu-id="788ca-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="788ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="788ca-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="788ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="788ca-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="788ca-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="788ca-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="788ca-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="788ca-107">singleElementOperation: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="788ca-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="788ca-108">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="788ca-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="788ca-109">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="788ca-109">register : 'T[]</span></span>

<span data-ttu-id="788ca-110">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="788ca-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="788ca-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="788ca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="788ca-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="788ca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="788ca-113">'C</span><span class="sxs-lookup"><span data-stu-id="788ca-113">'T</span></span>

<span data-ttu-id="788ca-114">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="788ca-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="788ca-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="788ca-115">See Also</span></span>

- [<span data-ttu-id="788ca-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="788ca-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="788ca-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="788ca-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="788ca-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="788ca-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)