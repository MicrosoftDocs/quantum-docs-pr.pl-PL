---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825754"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="0c97e-102">MeasureStabilizerGenerators, operacja</span><span class="sxs-lookup"><span data-stu-id="0c97e-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="0c97e-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0c97e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0c97e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c97e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c97e-105">Mierzy dany zestaw generatorów grupy stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="0c97e-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="0c97e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0c97e-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="0c97e-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="0c97e-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="0c97e-108">Tablica operatorów multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="0c97e-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="0c97e-109">Na przykład, `stabilizerGroup[0]` jest listą macierzy Pauli z jednym qubitm, który jest produktem, który jest generatorem stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="0c97e-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="0c97e-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="0c97e-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="0c97e-111">Tablica qubits, w której jest zdefiniowany kod stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="0c97e-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="0c97e-112">Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="0c97e-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="0c97e-113">Operacja określająca sposób mierzenia operatora multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="0c97e-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="0c97e-114">Wynik: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="0c97e-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="0c97e-115">Wynik pomiarów.</span><span class="sxs-lookup"><span data-stu-id="0c97e-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c97e-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0c97e-116">Remarks</span></span>

<span data-ttu-id="0c97e-117">Nie sprawdza to, czy dany zestaw generatorów jest podróży.</span><span class="sxs-lookup"><span data-stu-id="0c97e-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="0c97e-118">Jeśli nie są one podróży, wynik pomiarów może być dowolny.</span><span class="sxs-lookup"><span data-stu-id="0c97e-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>