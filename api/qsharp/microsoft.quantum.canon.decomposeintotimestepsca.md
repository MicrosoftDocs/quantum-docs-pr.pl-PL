---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716333"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="b6cfb-102">DecomposeIntoTimeStepsCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="b6cfb-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="b6cfb-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6cfb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6cfb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6cfb-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="b6cfb-105">DecomposeIntoTimeStepsCA jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="b6cfb-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="b6cfb-106">Użyj <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="b6cfb-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b6cfb-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b6cfb-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="b6cfb-108">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6cfb-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="b6cfb-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="b6cfb-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="b6cfb-110">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6cfb-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="b6cfb-111">Output: ([Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="b6cfb-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b6cfb-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b6cfb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6cfb-113">'C</span><span class="sxs-lookup"><span data-stu-id="b6cfb-113">'T</span></span>

