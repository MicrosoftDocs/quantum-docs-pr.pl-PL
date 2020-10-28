---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717808"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="731f1-102">ApplyPauliFromBitString, operacja</span><span class="sxs-lookup"><span data-stu-id="731f1-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="731f1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="731f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="731f1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="731f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="731f1-105">Stosuje operator Pauli na każdym qubit w tablicy, jeśli odpowiedni bit tablicy logicznej jest zgodny z danymi wejściowymi.</span><span class="sxs-lookup"><span data-stu-id="731f1-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="731f1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="731f1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="731f1-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="731f1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="731f1-108">Operator Pauli do zastosowania do `qubits[idx]` WHERE `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="731f1-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="731f1-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="731f1-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="731f1-110">Zastosuj Pauli, jeśli bit jest tą wartością</span><span class="sxs-lookup"><span data-stu-id="731f1-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="731f1-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="731f1-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="731f1-112">Rejestr logiczny określający, który odpowiada qubit w `qubits` usłudze powinien działać na</span><span class="sxs-lookup"><span data-stu-id="731f1-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="731f1-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="731f1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="731f1-114">Rejestr Quantum, dla którego można wybiórczo zastosować określonego operatora Pauli</span><span class="sxs-lookup"><span data-stu-id="731f1-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="731f1-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="731f1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="731f1-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="731f1-116">Remarks</span></span>

<span data-ttu-id="731f1-117">Tablica logiczna i rejestr Quantum muszą mieć równej długości.</span><span class="sxs-lookup"><span data-stu-id="731f1-117">The Boolean array and the quantum register must be of equal length.</span></span>