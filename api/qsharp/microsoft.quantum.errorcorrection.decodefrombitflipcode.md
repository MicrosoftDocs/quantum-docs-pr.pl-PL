---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712483"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="e4d24-102">DecodeFromBitFlipCode, operacja</span><span class="sxs-lookup"><span data-stu-id="e4d24-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="e4d24-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e4d24-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e4d24-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4d24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4d24-105">Dekoduje z kodu [3, 1, 3]/⟦ 3, 1, 1 ⟧ bitowego.</span><span class="sxs-lookup"><span data-stu-id="e4d24-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="e4d24-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e4d24-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="e4d24-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e4d24-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e4d24-108">Blok kodu kodu bitowego.</span><span class="sxs-lookup"><span data-stu-id="e4d24-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="e4d24-109">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="e4d24-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="e4d24-110">Krotka danych zakodowana w rejestrze logicznym i pomocnicza qubits użyta do reprezentowania Syndrome.</span><span class="sxs-lookup"><span data-stu-id="e4d24-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4d24-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e4d24-111">See Also</span></span>

- [<span data-ttu-id="e4d24-112">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e4d24-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="e4d24-113">Microsoft. Quantum. ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="e4d24-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)