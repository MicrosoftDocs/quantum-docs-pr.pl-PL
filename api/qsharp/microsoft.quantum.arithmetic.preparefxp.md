---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 31ed1a170a47c77c21aa8b5c291860e422af2e3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845794"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="3167c-102">PrepareFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="3167c-102">PrepareFxP operation</span></span>

<span data-ttu-id="3167c-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3167c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3167c-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3167c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3167c-105">Zainicjuj liczbę stałych punktów Quantum do klasycznej stałej.</span><span class="sxs-lookup"><span data-stu-id="3167c-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3167c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3167c-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="3167c-107">stała: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3167c-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3167c-108">Stała, do której ma zostać zainicjowana stała liczba zmiennoprzecinkowa.</span><span class="sxs-lookup"><span data-stu-id="3167c-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="3167c-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3167c-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3167c-110">Liczba stałych punktów (typu FixedPoint) do zainicjowania.</span><span class="sxs-lookup"><span data-stu-id="3167c-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3167c-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3167c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

