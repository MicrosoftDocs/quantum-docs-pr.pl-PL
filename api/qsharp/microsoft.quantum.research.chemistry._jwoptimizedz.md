---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: Operacja _JWOptimizedZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724630"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="1220f-102">Operacja _JWOptimizedZ</span><span class="sxs-lookup"><span data-stu-id="1220f-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="1220f-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1220f-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="1220f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1220f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1220f-105">Stosuje obrót rz z nielewę do podwójnej fazy w fazie szacowania fazy.</span><span class="sxs-lookup"><span data-stu-id="1220f-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1220f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1220f-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="1220f-107">kąt: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1220f-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1220f-108">Kąt obrotu rz.</span><span class="sxs-lookup"><span data-stu-id="1220f-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="1220f-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1220f-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1220f-110">Qubit, który określa znak ewolucji czasu.</span><span class="sxs-lookup"><span data-stu-id="1220f-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="1220f-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1220f-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="1220f-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1220f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

