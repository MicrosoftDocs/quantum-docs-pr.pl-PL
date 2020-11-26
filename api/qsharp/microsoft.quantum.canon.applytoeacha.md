---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217802"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="1898a-102">ApplyToEachA, operacja</span><span class="sxs-lookup"><span data-stu-id="1898a-102">ApplyToEachA operation</span></span>

<span data-ttu-id="1898a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1898a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1898a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1898a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1898a-105">Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="1898a-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="1898a-106">Modyfikator `A` wskazuje, że operacja pojedynczego qubit jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="1898a-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="1898a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1898a-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="1898a-108">singleElementOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="1898a-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1898a-109">Operacja do zastosowania do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="1898a-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="1898a-110">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="1898a-110">register : 'T[]</span></span>

<span data-ttu-id="1898a-111">Tablica qubits, na której ma zostać zastosowana dana operacja.</span><span class="sxs-lookup"><span data-stu-id="1898a-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1898a-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1898a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1898a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1898a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1898a-114">'C</span><span class="sxs-lookup"><span data-stu-id="1898a-114">'T</span></span>

<span data-ttu-id="1898a-115">Obiekt docelowy, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="1898a-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="1898a-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1898a-116">See Also</span></span>

- [<span data-ttu-id="1898a-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="1898a-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)