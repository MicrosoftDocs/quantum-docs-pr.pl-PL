---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712749"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="30c9e-102">EqualityWithinToleranceFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="30c9e-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="30c9e-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="30c9e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="30c9e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30c9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30c9e-105">Reprezentuje zastrzeżenie, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do odporności absolutnej.</span><span class="sxs-lookup"><span data-stu-id="30c9e-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="30c9e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="30c9e-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="30c9e-107">rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30c9e-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30c9e-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="30c9e-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="30c9e-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30c9e-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30c9e-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="30c9e-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="30c9e-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30c9e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30c9e-112">Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.</span><span class="sxs-lookup"><span data-stu-id="30c9e-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="30c9e-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30c9e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

