---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859219"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="a9ba3-102">ApplyUnitary, operacja</span><span class="sxs-lookup"><span data-stu-id="a9ba3-102">ApplyUnitary operation</span></span>

<span data-ttu-id="a9ba3-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a9ba3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a9ba3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9ba3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9ba3-105">Stosuje bramę zdefiniowaną przez 2 ^ n x 2 ^ n macierz jednostkową.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="a9ba3-106">Kończy się niepowodzeniem, jeśli macierz nie jest jednostką lub ma zły rozmiar.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a9ba3-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a9ba3-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="a9ba3-108">Jednostka jednostkowa: [złożona](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="a9ba3-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="a9ba3-109">2 ^ n x 2 ^ n macierz jednostkowa opisującą operację.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="a9ba3-110">Jeśli macierz nie jest jednostką lub nie ma odpowiedniego rozmiaru, zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a9ba3-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9ba3-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9ba3-112">Qubits, do którego zastosowano rejestr operacji o długości n.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9ba3-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9ba3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

