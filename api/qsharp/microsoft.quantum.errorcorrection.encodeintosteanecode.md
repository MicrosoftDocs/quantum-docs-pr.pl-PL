---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712390"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="f4218-102">EncodeIntoSteaneCode, operacja</span><span class="sxs-lookup"><span data-stu-id="f4218-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="f4218-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f4218-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f4218-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4218-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4218-105">Operacja kodowania, która mapuje niezakodowany rejestr Quantum na zakodowany rejestr Quantum w ⟦ 7, 1, 3 ⟧ Steane Quantum.</span><span class="sxs-lookup"><span data-stu-id="f4218-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="f4218-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f4218-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="f4218-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f4218-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f4218-108">Rejestr qubit, który zawiera niezakodowany stan Quantum</span><span class="sxs-lookup"><span data-stu-id="f4218-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="f4218-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f4218-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f4218-110">Rejestr qubit, który jest początkowo zerem i jest dodawany do systemu Quantum, aby można było wykonać operację kodowania</span><span class="sxs-lookup"><span data-stu-id="f4218-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="f4218-111">Wynik: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="f4218-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="f4218-112">Rejestr Quantum przechowujący stan po zastosowaniu kodera Steane</span><span class="sxs-lookup"><span data-stu-id="f4218-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="f4218-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f4218-113">See Also</span></span>

- [<span data-ttu-id="f4218-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="f4218-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="f4218-115">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="f4218-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)