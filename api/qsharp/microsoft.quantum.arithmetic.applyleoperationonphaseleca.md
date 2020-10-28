---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: ApplyLEOperationOnPhaseLECA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 9d70e89fe4186244361d80252b856878772eda30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721617"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="0b6ea-102">ApplyLEOperationOnPhaseLECA, operacja</span><span class="sxs-lookup"><span data-stu-id="0b6ea-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="0b6ea-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0b6ea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0b6ea-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b6ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b6ea-105">Stosuje operację, która pobiera <xref:microsoft.quantum.arithmetic.phaselittleendian> Rejestr jako dane wejściowe w docelowym rejestrze typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="0b6ea-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="0b6ea-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0b6ea-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="0b6ea-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL</span><span class="sxs-lookup"><span data-stu-id="0b6ea-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0b6ea-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="0b6ea-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="0b6ea-109">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0b6ea-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="0b6ea-110">Rejestr, do którego zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="0b6ea-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b6ea-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b6ea-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0b6ea-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0b6ea-112">Remarks</span></span>

<span data-ttu-id="0b6ea-113">Rejestr jest przekształcany `LittleEndian` przez użycie programu <xref:microsoft.quantum.canon.qftle> i jest następnie zwracany do oryginalnej reprezentacji po zastosowaniu programu `op` .</span><span class="sxs-lookup"><span data-stu-id="0b6ea-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b6ea-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0b6ea-114">See Also</span></span>

- [<span data-ttu-id="0b6ea-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="0b6ea-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="0b6ea-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="0b6ea-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="0b6ea-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="0b6ea-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)