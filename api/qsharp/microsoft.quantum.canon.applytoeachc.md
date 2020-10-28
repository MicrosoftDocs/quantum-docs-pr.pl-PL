---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717565"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="7f620-102">ApplyToEachC, operacja</span><span class="sxs-lookup"><span data-stu-id="7f620-102">ApplyToEachC operation</span></span>

<span data-ttu-id="7f620-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7f620-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7f620-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f620-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f620-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="7f620-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="7f620-106">Modyfikator `C` wskazuje, że operacje pojedynczej qubit są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="7f620-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7f620-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7f620-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="7f620-108">singleElementOperation: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7f620-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7f620-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="7f620-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7f620-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="7f620-110">register : 'T[]</span></span>

<span data-ttu-id="7f620-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="7f620-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f620-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f620-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7f620-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7f620-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f620-114">'C</span><span class="sxs-lookup"><span data-stu-id="7f620-114">'T</span></span>

<span data-ttu-id="7f620-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="7f620-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f620-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7f620-116">See Also</span></span>

- [<span data-ttu-id="7f620-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="7f620-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)