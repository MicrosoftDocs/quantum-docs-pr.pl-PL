---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828746"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="1472a-102">EqualityWithinToleranceFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="1472a-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="1472a-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1472a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1472a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1472a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1472a-105">Reprezentuje zastrzeżenie, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do odporności absolutnej.</span><span class="sxs-lookup"><span data-stu-id="1472a-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1472a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1472a-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="1472a-107">rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1472a-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1472a-108">Liczba, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="1472a-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="1472a-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1472a-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1472a-110">Oczekiwana wartość.</span><span class="sxs-lookup"><span data-stu-id="1472a-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1472a-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1472a-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1472a-112">Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.</span><span class="sxs-lookup"><span data-stu-id="1472a-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1472a-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1472a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

