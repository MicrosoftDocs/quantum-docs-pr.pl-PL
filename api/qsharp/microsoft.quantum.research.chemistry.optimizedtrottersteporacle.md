---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 04b1ea457277e0681596cb564fae3782a2d09db9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229821"
---
# <a name="optimizedtrottersteporacle-function"></a><span data-ttu-id="b3d6b-102">OptimizedTrotterStepOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="b3d6b-102">OptimizedTrotterStepOracle function</span></span>

<span data-ttu-id="b3d6b-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b3d6b-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b3d6b-104">Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b3d6b-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="b3d6b-105">Zwraca zoptymalizowaną operację kroku Trotter i parametry niezbędne do jej uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="b3d6b-105">Returns optimized Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="b3d6b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b3d6b-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="b3d6b-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="b3d6b-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="b3d6b-108">Hamiltonian opisane przez `JordanWignerEncodingData` Format.</span><span class="sxs-lookup"><span data-stu-id="b3d6b-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="b3d6b-109">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3d6b-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3d6b-110">Rozmiar kroku integratora Trotter.</span><span class="sxs-lookup"><span data-stu-id="b3d6b-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="b3d6b-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3d6b-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3d6b-112">Kolejność integratora Trotter.</span><span class="sxs-lookup"><span data-stu-id="b3d6b-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a><span data-ttu-id="b3d6b-113">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL))</span><span class="sxs-lookup"><span data-stu-id="b3d6b-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl))</span></span>

<span data-ttu-id="b3d6b-114">Krotka, gdzie: `Int` jest liczbą qubits przydzieloną, `Double` jest `1.0/trotterStepSize` , a operacja jest krokiem Trotter.</span><span class="sxs-lookup"><span data-stu-id="b3d6b-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>