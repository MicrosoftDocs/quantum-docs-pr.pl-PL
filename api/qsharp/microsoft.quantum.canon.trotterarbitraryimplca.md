---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715288"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="5a3b6-102">TrotterArbitraryImplCA, operacja</span><span class="sxs-lookup"><span data-stu-id="5a3b6-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="5a3b6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a3b6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a3b6-105">Cykliczna implementacja integratora Trotter — Suzuki.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="5a3b6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5a3b6-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="5a3b6-107">kolejność: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a3b6-108">Kolejność integratora Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="5a3b6-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a3b6-110">Liczba operacji do rozdzielenia na etapy czasu.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5a3b6-111">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="5a3b6-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5a3b6-112">Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) i rejestr Quantum (typ `'T` ) dla dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5a3b6-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a3b6-114">Mnożnik na rozmiar każdego kroku symulacji.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="5a3b6-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="5a3b6-115">target : 'T</span></span>

<span data-ttu-id="5a3b6-116">Rejestr Quantum, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="5a3b6-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a3b6-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a3b6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a3b6-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5a3b6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a3b6-119">'C</span><span class="sxs-lookup"><span data-stu-id="5a3b6-119">'T</span></span>

<span data-ttu-id="5a3b6-120">Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="5a3b6-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>