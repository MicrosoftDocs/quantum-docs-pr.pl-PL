---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: 62f6f4ff372143228de007c98a23697022fcfd24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856100"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="50218-102">SampleTransformedContinuousDistribution, operacja</span><span class="sxs-lookup"><span data-stu-id="50218-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="50218-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="50218-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="50218-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="50218-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="50218-105">Operacja tylko wewnętrzna służąca do próbkowania z przekształconych dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="50218-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="50218-106">Powinien być używany tylko za pośrednictwem częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="50218-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="50218-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="50218-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="50218-108">transformacja: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50218-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="50218-109">dystrybucja: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="50218-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="50218-110">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50218-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

