---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834249"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="71c39-102">BoolArrayAsPauli, funkcja</span><span class="sxs-lookup"><span data-stu-id="71c39-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="71c39-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="71c39-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="71c39-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71c39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71c39-105">Podanym ciągiem bitowym zwraca operator qubit Pauli, reprezentowany jako tablica operatorów typu Single-qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="71c39-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="71c39-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="71c39-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="71c39-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="71c39-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="71c39-108">Operator Pauli do zastosowania do qubits, gdzie `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="71c39-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="71c39-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="71c39-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="71c39-110">Zastosuj Pauli, jeśli jest to wartość bitowa.</span><span class="sxs-lookup"><span data-stu-id="71c39-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="71c39-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="71c39-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="71c39-112">Tablica logiczna.</span><span class="sxs-lookup"><span data-stu-id="71c39-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="71c39-113">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="71c39-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="71c39-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71c39-114">Remarks</span></span>

<span data-ttu-id="71c39-115">Tablica logiczna i rejestr Quantum muszą mieć równej długości.</span><span class="sxs-lookup"><span data-stu-id="71c39-115">The Boolean array and the quantum register must be of equal length.</span></span>