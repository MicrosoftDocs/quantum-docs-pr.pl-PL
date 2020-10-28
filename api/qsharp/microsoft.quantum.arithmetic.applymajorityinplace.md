---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721596"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="f55a1-102">ApplyMajorityInPlace, operacja</span><span class="sxs-lookup"><span data-stu-id="f55a1-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="f55a1-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f55a1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f55a1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f55a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f55a1-105">Stosuje qubit większość operacji w miejscu rejestracji qubits.</span><span class="sxs-lookup"><span data-stu-id="f55a1-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f55a1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f55a1-106">Description</span></span>

<span data-ttu-id="f55a1-107">Ta operacja oblicza większość funkcji w miejscu na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="f55a1-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="f55a1-108">Jeśli qubit danych wyjściowych jako $z $ i wejściowy qubits jako $x $ i $y $, operacja wykonuje następujące przekształcenia: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="f55a1-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="f55a1-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f55a1-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="f55a1-110">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f55a1-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f55a1-111">Pierwszy wejściowy qubit.</span><span class="sxs-lookup"><span data-stu-id="f55a1-111">First input qubit.</span></span> <span data-ttu-id="f55a1-112">Należy zauważyć, że dane wyjściowe są obliczane w miejscu i przechowywane w tym qubit.</span><span class="sxs-lookup"><span data-stu-id="f55a1-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="f55a1-113">dane wejściowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f55a1-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f55a1-114">Drugi i trzeci wejściowy qubits.</span><span class="sxs-lookup"><span data-stu-id="f55a1-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f55a1-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f55a1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

