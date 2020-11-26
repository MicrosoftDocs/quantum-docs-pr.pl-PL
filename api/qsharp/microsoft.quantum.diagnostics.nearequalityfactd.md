---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201516"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="f5511-102">NearEqualityFactD, funkcja</span><span class="sxs-lookup"><span data-stu-id="f5511-102">NearEqualityFactD function</span></span>

<span data-ttu-id="f5511-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f5511-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f5511-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5511-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5511-105">Potwierdza, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do małej tolerancji o wartości 1e-10.</span><span class="sxs-lookup"><span data-stu-id="f5511-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="f5511-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f5511-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="f5511-107">rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5511-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5511-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="f5511-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="f5511-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5511-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5511-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="f5511-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5511-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5511-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5511-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f5511-112">Remarks</span></span>

<span data-ttu-id="f5511-113">Jest to równoznaczne <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> z stałe odporności na $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="f5511-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>