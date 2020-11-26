---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 275f31ea636d15eb0d78e5148e8af6b58d22729d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209659"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="329c6-102">ApplyCCNOTChain, operacja</span><span class="sxs-lookup"><span data-stu-id="329c6-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="329c6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="329c6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="329c6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="329c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="329c6-105">Implementuje kaskadowe bramy CCNOT kontrolowane na odpowiednich bitach dwóch rejestrów qubit, działając na następnym qubit jednego z rejestrów.</span><span class="sxs-lookup"><span data-stu-id="329c6-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="329c6-106">Począwszy od qubits na pozycji 0 w obu rejestrach jako kontrolki, CCNOT jest zastosowany do qubit na pozycji 1 rejestru docelowego, a następnie kontrolowane przez qubits na pozycji 1 działającej na qubit w pozycji 2 w rejestrze docelowym itd., kończąc z akcją na docelowym qubit na pozycji `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="329c6-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="329c6-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="329c6-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="329c6-108">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="329c6-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="329c6-109">Rejestr qubit używany tylko w kontrolkach.</span><span class="sxs-lookup"><span data-stu-id="329c6-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="329c6-110">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="329c6-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="329c6-111">Rejestr qubit używany w kontrolkach i jako element docelowy.</span><span class="sxs-lookup"><span data-stu-id="329c6-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="329c6-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="329c6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="329c6-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="329c6-113">Remarks</span></span>

<span data-ttu-id="329c6-114">Docelowy rejestr qubit musi mieć jeden qubit więcej niż inny rejestr.</span><span class="sxs-lookup"><span data-stu-id="329c6-114">The target qubit register must have one qubit more than the other register.</span></span>