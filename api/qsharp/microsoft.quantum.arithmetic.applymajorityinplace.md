---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190738"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="7d8b7-102">ApplyMajorityInPlace, operacja</span><span class="sxs-lookup"><span data-stu-id="7d8b7-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="7d8b7-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d8b7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d8b7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d8b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d8b7-105">Stosuje qubit większość operacji w miejscu rejestracji qubits.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7d8b7-106">Opis</span><span class="sxs-lookup"><span data-stu-id="7d8b7-106">Description</span></span>

<span data-ttu-id="7d8b7-107">Ta operacja oblicza większość funkcji w miejscu na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="7d8b7-108">Jeśli qubit danych wyjściowych jako $z $ i wejściowy qubits jako $x $ i $y $, operacja wykonuje następujące przekształcenia: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="7d8b7-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7d8b7-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="7d8b7-110">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d8b7-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d8b7-111">Pierwszy wejściowy qubit.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-111">First input qubit.</span></span> <span data-ttu-id="7d8b7-112">Należy zauważyć, że dane wyjściowe są obliczane w miejscu i przechowywane w tym qubit.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="7d8b7-113">dane wejściowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d8b7-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d8b7-114">Drugi i trzeci wejściowy qubits.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d8b7-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d8b7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

