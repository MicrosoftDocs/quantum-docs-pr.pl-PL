---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712399"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="c4724-102">EncodeIntoFiveQubitCode, operacja</span><span class="sxs-lookup"><span data-stu-id="c4724-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="c4724-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c4724-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c4724-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4724-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4724-105">Koduje kod Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="c4724-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="c4724-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c4724-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="c4724-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c4724-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c4724-108">Qubit reprezentujący niezakodowany stan.</span><span class="sxs-lookup"><span data-stu-id="c4724-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="c4724-109">Ta tablica `Qubit[]` ma długość 1.</span><span class="sxs-lookup"><span data-stu-id="c4724-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="c4724-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c4724-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c4724-111">Rejestr pomocniczej qubits, który będzie używany do reprezentowania stanu zaszyfrowanego.</span><span class="sxs-lookup"><span data-stu-id="c4724-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="c4724-112">Wynik: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c4724-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c4724-113">Tablica fizycznych qubits typu `LogicalRegister` , który przechowuje zakodowany stan.</span><span class="sxs-lookup"><span data-stu-id="c4724-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4724-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c4724-114">See Also</span></span>

- [<span data-ttu-id="c4724-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c4724-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)