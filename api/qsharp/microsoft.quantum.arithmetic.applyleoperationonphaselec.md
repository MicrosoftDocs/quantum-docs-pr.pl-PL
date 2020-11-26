---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: ApplyLEOperationOnPhaseLEC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: dafe27f66f967fb641a8898672e124c0a51fe687
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190840"
---
# <a name="applyleoperationonphaselec-operation"></a><span data-ttu-id="dc497-102">ApplyLEOperationOnPhaseLEC, operacja</span><span class="sxs-lookup"><span data-stu-id="dc497-102">ApplyLEOperationOnPhaseLEC operation</span></span>

<span data-ttu-id="dc497-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dc497-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dc497-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc497-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc497-105">Stosuje operację, która pobiera <xref:microsoft.quantum.arithmetic.phaselittleendian> Rejestr jako dane wejściowe w docelowym rejestrze typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="dc497-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="dc497-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dc497-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="dc497-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="dc497-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dc497-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="dc497-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="dc497-109">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc497-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="dc497-110">Rejestr, do którego zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="dc497-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc497-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc497-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc497-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc497-112">Remarks</span></span>

<span data-ttu-id="dc497-113">Rejestr jest przekształcany `LittleEndian` przez użycie programu <xref:microsoft.quantum.canon.qftle> i jest następnie zwracany do oryginalnej reprezentacji po zastosowaniu programu `op` .</span><span class="sxs-lookup"><span data-stu-id="dc497-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc497-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dc497-114">See Also</span></span>

- [<span data-ttu-id="dc497-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="dc497-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="dc497-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="dc497-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="dc497-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="dc497-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)