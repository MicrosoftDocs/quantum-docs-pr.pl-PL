---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200632"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="08f7b-102">MeasureStabilizerGenerators, operacja</span><span class="sxs-lookup"><span data-stu-id="08f7b-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="08f7b-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="08f7b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="08f7b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08f7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08f7b-105">Mierzy dany zestaw generatorów grupy stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="08f7b-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="08f7b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="08f7b-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="08f7b-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="08f7b-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="08f7b-108">Tablica operatorów multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="08f7b-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="08f7b-109">Na przykład, `stabilizerGroup[0]` jest listą macierzy Pauli z jednym qubitm, który jest produktem, który jest generatorem stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="08f7b-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="08f7b-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="08f7b-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="08f7b-111">Tablica qubits, w której jest zdefiniowany kod stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="08f7b-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="08f7b-112">Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="08f7b-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="08f7b-113">Operacja określająca sposób mierzenia operatora multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="08f7b-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="08f7b-114">Wynik: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="08f7b-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="08f7b-115">Wynik pomiarów.</span><span class="sxs-lookup"><span data-stu-id="08f7b-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="08f7b-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="08f7b-116">Remarks</span></span>

<span data-ttu-id="08f7b-117">Nie sprawdza to, czy dany zestaw generatorów jest podróży.</span><span class="sxs-lookup"><span data-stu-id="08f7b-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="08f7b-118">Jeśli nie są one podróży, wynik pomiarów może być dowolny.</span><span class="sxs-lookup"><span data-stu-id="08f7b-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>