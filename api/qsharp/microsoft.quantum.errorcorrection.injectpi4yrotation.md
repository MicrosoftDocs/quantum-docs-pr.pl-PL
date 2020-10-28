---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712320"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="a9095-102">InjectPi4YRotation, operacja</span><span class="sxs-lookup"><span data-stu-id="a9095-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="a9095-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a9095-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a9095-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9095-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9095-105">Obraca pojedynczy qubit o π/4 o oś Y.</span><span class="sxs-lookup"><span data-stu-id="a9095-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a9095-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a9095-106">Description</span></span>

<span data-ttu-id="a9095-107">Wykonuje rotację π/4 `Y` .</span><span class="sxs-lookup"><span data-stu-id="a9095-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="a9095-108">Obrót jest wykonywany przez zużywanie stanu Magic; oznacza to, że kopia stanu $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} .</span><span class="sxs-lookup"><span data-stu-id="a9095-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="a9095-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a9095-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a9095-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a9095-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="a9095-111">dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a9095-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a9095-112">Qubit, który ma zostać obrócony o $Y $ przez $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="a9095-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="a9095-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a9095-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a9095-114">Qubit początkowo w stanie Magic.</span><span class="sxs-lookup"><span data-stu-id="a9095-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="a9095-115">Następująca aplikacja `magic` jest zwracana do stanu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a9095-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9095-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9095-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a9095-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a9095-117">Remarks</span></span>

<span data-ttu-id="a9095-118">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="a9095-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="a9095-119">oraz</span><span class="sxs-lookup"><span data-stu-id="a9095-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="a9095-120">Ta operacja obsługuje `Adjoint` Funktor, w którym wykorzystano ten sam stan Magic, ale efektem na qubit danych jest wartość $-\ Pi/4 $ $Y $-Rotation.</span><span class="sxs-lookup"><span data-stu-id="a9095-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>