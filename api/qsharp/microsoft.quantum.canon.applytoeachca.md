---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717551"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="b85ef-102">ApplyToEachCA, operacja</span><span class="sxs-lookup"><span data-stu-id="b85ef-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="b85ef-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b85ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b85ef-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b85ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b85ef-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="b85ef-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="b85ef-106">Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="b85ef-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b85ef-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b85ef-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="b85ef-108">singleElementOperation: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="b85ef-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b85ef-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="b85ef-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="b85ef-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="b85ef-110">register : 'T[]</span></span>

<span data-ttu-id="b85ef-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="b85ef-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b85ef-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b85ef-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b85ef-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b85ef-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b85ef-114">'C</span><span class="sxs-lookup"><span data-stu-id="b85ef-114">'T</span></span>

<span data-ttu-id="b85ef-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="b85ef-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="b85ef-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b85ef-116">See Also</span></span>

- [<span data-ttu-id="b85ef-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="b85ef-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)