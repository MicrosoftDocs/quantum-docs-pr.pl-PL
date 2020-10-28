---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712651"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="8f3a8-102">NearEqualityFactD, funkcja</span><span class="sxs-lookup"><span data-stu-id="8f3a8-102">NearEqualityFactD function</span></span>

<span data-ttu-id="8f3a8-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8f3a8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8f3a8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f3a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f3a8-105">Potwierdza, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do małej tolerancji o wartości 1e-10.</span><span class="sxs-lookup"><span data-stu-id="8f3a8-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="8f3a8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f3a8-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="8f3a8-107">rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f3a8-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f3a8-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="8f3a8-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="8f3a8-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f3a8-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f3a8-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="8f3a8-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f3a8-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f3a8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8f3a8-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8f3a8-112">Remarks</span></span>

<span data-ttu-id="8f3a8-113">Jest to równoznaczne <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> z stałe odporności na $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="8f3a8-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>