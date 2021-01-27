---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841492"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="c4b45-102">ApplyToEachCA, operacja</span><span class="sxs-lookup"><span data-stu-id="c4b45-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="c4b45-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4b45-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4b45-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4b45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4b45-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="c4b45-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="c4b45-106">Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="c4b45-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c4b45-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c4b45-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c4b45-108">singleElementOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="c4b45-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c4b45-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4b45-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c4b45-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="c4b45-110">register : 'T[]</span></span>

<span data-ttu-id="c4b45-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="c4b45-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4b45-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4b45-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4b45-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c4b45-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4b45-114">'C</span><span class="sxs-lookup"><span data-stu-id="c4b45-114">'T</span></span>

<span data-ttu-id="c4b45-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="c4b45-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="c4b45-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="c4b45-116">Example</span></span>

<span data-ttu-id="c4b45-117">Przygotuj stan qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="c4b45-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="c4b45-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c4b45-118">See Also</span></span>

- [<span data-ttu-id="c4b45-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="c4b45-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)