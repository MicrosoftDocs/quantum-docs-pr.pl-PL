---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200802"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="d6792-102">InjectPi4YRotation, operacja</span><span class="sxs-lookup"><span data-stu-id="d6792-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="d6792-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d6792-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d6792-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6792-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6792-105">Obraca pojedynczy qubit o π/4 o oś Y.</span><span class="sxs-lookup"><span data-stu-id="d6792-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="d6792-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d6792-106">Description</span></span>

<span data-ttu-id="d6792-107">Wykonuje rotację π/4 `Y` .</span><span class="sxs-lookup"><span data-stu-id="d6792-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="d6792-108">Obrót jest wykonywany przez zużywanie stanu Magic; oznacza to, że kopia stanu $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} .</span><span class="sxs-lookup"><span data-stu-id="d6792-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="d6792-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d6792-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d6792-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d6792-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="d6792-111">dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6792-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d6792-112">Qubit, który ma zostać obrócony o $Y $ przez $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="d6792-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="d6792-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6792-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d6792-114">Qubit początkowo w stanie Magic.</span><span class="sxs-lookup"><span data-stu-id="d6792-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="d6792-115">Następująca aplikacja `magic` jest zwracana do stanu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d6792-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6792-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6792-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6792-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d6792-117">Remarks</span></span>

<span data-ttu-id="d6792-118">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="d6792-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="d6792-119">oraz</span><span class="sxs-lookup"><span data-stu-id="d6792-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="d6792-120">Ta operacja obsługuje `Adjoint` Funktor, w którym wykorzystano ten sam stan Magic, ale efektem na qubit danych jest wartość $-\ Pi/4 $ $Y $-Rotation.</span><span class="sxs-lookup"><span data-stu-id="d6792-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>