---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721017"
---
# <a name="maj-operation"></a><span data-ttu-id="6814d-102">MAJ, operacja</span><span class="sxs-lookup"><span data-stu-id="6814d-102">MAJ operation</span></span>

<span data-ttu-id="6814d-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6814d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6814d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6814d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6814d-105">Powoduje to zastosowanie operacji większości w miejscu do 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="6814d-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="6814d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6814d-106">Description</span></span>

<span data-ttu-id="6814d-107">W przypadku określenia stanu docelowej qubit jako $ \ket{z} $ i wejścia Stanów danych wejściowych qubits jako $ \ket{x} $ i $ \ket{y} $, ta operacja wykonuje następującą transformację: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="6814d-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6814d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6814d-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="6814d-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6814d-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6814d-110">Pierwszy qubit wejściowy.</span><span class="sxs-lookup"><span data-stu-id="6814d-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="6814d-111">INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6814d-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6814d-112">Drugi wejściowy qubit.</span><span class="sxs-lookup"><span data-stu-id="6814d-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6814d-113">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6814d-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6814d-114">Qubit, na który zostanie zastosowana większość funkcji.</span><span class="sxs-lookup"><span data-stu-id="6814d-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6814d-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6814d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

