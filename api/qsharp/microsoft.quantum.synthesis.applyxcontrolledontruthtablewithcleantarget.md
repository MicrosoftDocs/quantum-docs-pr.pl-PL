---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203267"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="3e199-102">ApplyXControlledOnTruthTableWithCleanTarget, operacja</span><span class="sxs-lookup"><span data-stu-id="3e199-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="3e199-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3e199-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3e199-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e199-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e199-105">Stosuje @"microsoft.quantum.intrinsic.x" operację na `target` , jeśli funkcja logiczna `func` zwróci wartość true dla klasycznego przypisania w `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="3e199-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3e199-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3e199-106">Description</span></span>

<span data-ttu-id="3e199-107">Ta operacja implementuje szczególny przypadek @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , w którym element docelowy qubit jest znany jako w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="3e199-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="3e199-108">Implementacja wykorzystuje @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" bramy i.</span><span class="sxs-lookup"><span data-stu-id="3e199-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="3e199-109">Implementacja sąsiedniej operacji jest zoptymalizowana i używa obliczeń opartych na pomiarach.</span><span class="sxs-lookup"><span data-stu-id="3e199-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="3e199-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3e199-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="3e199-111">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3e199-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3e199-112">Tabela wartości logicznych prawdy reprezentowana jako duża liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="3e199-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="3e199-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e199-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e199-114">Rejestr kontroli qubits</span><span class="sxs-lookup"><span data-stu-id="3e199-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3e199-115">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e199-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e199-116">Element docelowy qubit (musi być w stanie $ \ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="3e199-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e199-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e199-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e199-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3e199-118">See Also</span></span>

- [<span data-ttu-id="3e199-119">Microsoft. Quantum. synteza. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="3e199-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)