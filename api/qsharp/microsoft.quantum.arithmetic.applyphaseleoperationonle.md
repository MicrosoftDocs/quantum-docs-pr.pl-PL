---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721548"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="c172c-102">ApplyPhaseLEOperationOnLE, operacja</span><span class="sxs-lookup"><span data-stu-id="c172c-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="c172c-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c172c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c172c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c172c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c172c-105">Stosuje operację, która pobiera <xref:microsoft.quantum.arithmetic.littleendian> Rejestr jako dane wejściowe w docelowym rejestrze typu <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="c172c-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c172c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c172c-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="c172c-107">op: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c172c-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c172c-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="c172c-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="c172c-109">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c172c-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c172c-110">Rejestr, do którego zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="c172c-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c172c-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c172c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c172c-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c172c-112">Remarks</span></span>

<span data-ttu-id="c172c-113">Rejestr jest przekształcany `PhaseLittleEndian` przez użycie programu <xref:microsoft.quantum.canon.qftle> i jest następnie zwracany do oryginalnej reprezentacji po zastosowaniu programu `op` .</span><span class="sxs-lookup"><span data-stu-id="c172c-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c172c-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c172c-114">See Also</span></span>

- [<span data-ttu-id="c172c-115">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="c172c-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="c172c-116">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="c172c-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="c172c-117">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="c172c-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)