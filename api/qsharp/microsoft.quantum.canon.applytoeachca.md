---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217751"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="ca443-102">ApplyToEachCA, operacja</span><span class="sxs-lookup"><span data-stu-id="ca443-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="ca443-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca443-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca443-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca443-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca443-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="ca443-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="ca443-106">Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="ca443-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ca443-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca443-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="ca443-108">singleElementOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="ca443-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ca443-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="ca443-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ca443-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="ca443-110">register : 'T[]</span></span>

<span data-ttu-id="ca443-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="ca443-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca443-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca443-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca443-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ca443-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca443-114">'C</span><span class="sxs-lookup"><span data-stu-id="ca443-114">'T</span></span>

<span data-ttu-id="ca443-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="ca443-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca443-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ca443-116">See Also</span></span>

- [<span data-ttu-id="ca443-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="ca443-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)