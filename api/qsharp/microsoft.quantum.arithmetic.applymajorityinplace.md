---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843725"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="e732b-102">ApplyMajorityInPlace, operacja</span><span class="sxs-lookup"><span data-stu-id="e732b-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="e732b-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e732b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e732b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e732b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e732b-105">Stosuje qubit większość operacji w miejscu rejestracji qubits.</span><span class="sxs-lookup"><span data-stu-id="e732b-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e732b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e732b-106">Description</span></span>

<span data-ttu-id="e732b-107">Ta operacja oblicza większość funkcji w miejscu na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="e732b-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="e732b-108">Jeśli qubit danych wyjściowych jako $z $ i wejściowy qubits jako $x $ i $y $, operacja wykonuje następujące przekształcenia: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="e732b-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="e732b-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e732b-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="e732b-110">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e732b-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e732b-111">Pierwszy wejściowy qubit.</span><span class="sxs-lookup"><span data-stu-id="e732b-111">First input qubit.</span></span> <span data-ttu-id="e732b-112">Należy zauważyć, że dane wyjściowe są obliczane w miejscu i przechowywane w tym qubit.</span><span class="sxs-lookup"><span data-stu-id="e732b-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="e732b-113">dane wejściowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e732b-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e732b-114">Drugi i trzeci wejściowy qubits.</span><span class="sxs-lookup"><span data-stu-id="e732b-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e732b-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e732b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

