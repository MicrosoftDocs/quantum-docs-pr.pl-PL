---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715927"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="9faf1-102">LogicalANDMeasAndFix, operacja</span><span class="sxs-lookup"><span data-stu-id="9faf1-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="9faf1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9faf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9faf1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9faf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9faf1-105">Oblicza wartość logiczną i wiele qubits.</span><span class="sxs-lookup"><span data-stu-id="9faf1-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9faf1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9faf1-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="9faf1-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9faf1-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9faf1-108">Qubits dane wejściowe do bramy z wieloma danymi wejściowymi i.</span><span class="sxs-lookup"><span data-stu-id="9faf1-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9faf1-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9faf1-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9faf1-110">Qubit, w którym są zapisywane dane wyjściowe i.</span><span class="sxs-lookup"><span data-stu-id="9faf1-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="9faf1-111">Przyjęto założenie, że zawsze zaczyna się w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9faf1-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9faf1-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9faf1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9faf1-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9faf1-113">Remarks</span></span>

<span data-ttu-id="9faf1-114">Gdy `ctrlRegister` ma dokładnie $2 $ qubits, jest to równoważne z `CCNOT` operacją, ale faza z fazą $e ^ {i \ pi/2} $ w $ \ket {001} $ i $-e ^ {i \ pi/2} $ w $ \ket {101} $ i $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="9faf1-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="9faf1-115">Sąsiednie rozwiązanie jest również metodą mierzenia i naprawiania, która jest odwrotnością oryginalnej operacji tylko w specjalnych przypadkach (zobacz odwołania), ale używa mniejszej liczby bram T-.</span><span class="sxs-lookup"><span data-stu-id="9faf1-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="9faf1-116">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="9faf1-116">References</span></span>

- [<span data-ttu-id="9faf1-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="9faf1-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)