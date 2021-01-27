---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844616"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="7058c-102">ApplyToEachA, operacja</span><span class="sxs-lookup"><span data-stu-id="7058c-102">ApplyToEachA operation</span></span>

<span data-ttu-id="7058c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7058c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7058c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7058c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7058c-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="7058c-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="7058c-106">Modyfikator `A` wskazuje, że operacja pojedynczego qubit jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="7058c-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7058c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7058c-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="7058c-108">singleElementOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="7058c-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7058c-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="7058c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7058c-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="7058c-110">register : 'T[]</span></span>

<span data-ttu-id="7058c-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="7058c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7058c-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7058c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7058c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7058c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7058c-114">'C</span><span class="sxs-lookup"><span data-stu-id="7058c-114">'T</span></span>

<span data-ttu-id="7058c-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="7058c-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="7058c-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="7058c-116">Example</span></span>

<span data-ttu-id="7058c-117">Przygotuj stan qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="7058c-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="7058c-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7058c-118">See Also</span></span>

- [<span data-ttu-id="7058c-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="7058c-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)