---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712404"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="bb73a-102">EncodeIntoBitFlipCode, operacja</span><span class="sxs-lookup"><span data-stu-id="bb73a-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="bb73a-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bb73a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bb73a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb73a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb73a-105">Koduje kod [3, 1, 3]/⟦ 3, 1, 1 ⟧ bitową.</span><span class="sxs-lookup"><span data-stu-id="bb73a-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="bb73a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bb73a-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="bb73a-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bb73a-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bb73a-108">Rejestr fizycznej qubits reprezentujący dane, które mają być chronione.</span><span class="sxs-lookup"><span data-stu-id="bb73a-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="bb73a-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bb73a-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bb73a-110">Rejestr pomocniczych qubits początkowo w stanie $ \ket {00} $, który ma być używany w kodowaniu danych do ochrony.</span><span class="sxs-lookup"><span data-stu-id="bb73a-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="bb73a-111">Wynik: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="bb73a-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="bb73a-112">Fizyczne i pomocnicze qubits używane w kodowaniu, reprezentowane jako rejestr logiczny.</span><span class="sxs-lookup"><span data-stu-id="bb73a-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb73a-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb73a-113">See Also</span></span>

- [<span data-ttu-id="bb73a-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="bb73a-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)