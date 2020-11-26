---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: ApplyLEOperationOnPhaseLECA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 4762eb17b4c11e46b5b94498b7fc8fd2f855c659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190687"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="cb44f-102">ApplyLEOperationOnPhaseLECA, operacja</span><span class="sxs-lookup"><span data-stu-id="cb44f-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="cb44f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cb44f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cb44f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb44f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb44f-105">Stosuje operację, która pobiera <xref:microsoft.quantum.arithmetic.phaselittleendian> Rejestr jako dane wejściowe w docelowym rejestrze typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="cb44f-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cb44f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cb44f-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="cb44f-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="cb44f-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cb44f-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cb44f-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="cb44f-109">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cb44f-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="cb44f-110">Rejestr, do którego zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="cb44f-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb44f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb44f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb44f-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cb44f-112">Remarks</span></span>

<span data-ttu-id="cb44f-113">Rejestr jest przekształcany `LittleEndian` przez użycie programu <xref:microsoft.quantum.canon.qftle> i jest następnie zwracany do oryginalnej reprezentacji po zastosowaniu programu `op` .</span><span class="sxs-lookup"><span data-stu-id="cb44f-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb44f-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb44f-114">See Also</span></span>

- [<span data-ttu-id="cb44f-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="cb44f-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="cb44f-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="cb44f-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="cb44f-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="cb44f-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)