---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: ApplyLEOperationOnPhaseLEA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 408bd4e5d7146a74d7aec233765a63b2086b8ede
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190857"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="5f30a-102">ApplyLEOperationOnPhaseLEA, operacja</span><span class="sxs-lookup"><span data-stu-id="5f30a-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="5f30a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5f30a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5f30a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f30a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f30a-105">Stosuje operację, która pobiera <xref:microsoft.quantum.arithmetic.phaselittleendian> Rejestr jako dane wejściowe w docelowym rejestrze typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="5f30a-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5f30a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5f30a-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="5f30a-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian jest korektą</span><span class="sxs-lookup"><span data-stu-id="5f30a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5f30a-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5f30a-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="5f30a-109">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5f30a-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="5f30a-110">Rejestr, do którego zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="5f30a-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5f30a-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f30a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5f30a-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5f30a-112">Remarks</span></span>

<span data-ttu-id="5f30a-113">Rejestr jest przekształcany `LittleEndian` przez użycie programu <xref:microsoft.quantum.canon.qftle> i jest następnie zwracany do oryginalnej reprezentacji po zastosowaniu programu `op` .</span><span class="sxs-lookup"><span data-stu-id="5f30a-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f30a-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f30a-114">See Also</span></span>

- [<span data-ttu-id="5f30a-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="5f30a-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="5f30a-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="5f30a-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="5f30a-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="5f30a-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)