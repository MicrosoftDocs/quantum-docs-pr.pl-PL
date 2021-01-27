---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840102"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="b8923-102">Trotter1ImplCA, operacja</span><span class="sxs-lookup"><span data-stu-id="b8923-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="b8923-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b8923-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b8923-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8923-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8923-105">Implementacja integratora pierwszej kolejności (Trotter – Suzuki).</span><span class="sxs-lookup"><span data-stu-id="b8923-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b8923-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b8923-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="b8923-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8923-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8923-108">Liczba operacji do rozdzielenia na etapy czasu.</span><span class="sxs-lookup"><span data-stu-id="b8923-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="b8923-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="b8923-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b8923-110">Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) i rejestr Quantum (typ `'T` ) dla dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="b8923-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b8923-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8923-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8923-112">Mnożnik na rozmiar każdego kroku symulacji.</span><span class="sxs-lookup"><span data-stu-id="b8923-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="b8923-113">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="b8923-113">target : 'T</span></span>

<span data-ttu-id="b8923-114">Rejestr Quantum, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="b8923-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8923-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8923-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b8923-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b8923-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8923-117">'C</span><span class="sxs-lookup"><span data-stu-id="b8923-117">'T</span></span>

<span data-ttu-id="b8923-118">Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="b8923-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="b8923-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="b8923-119">Example</span></span>

<span data-ttu-id="b8923-120">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="b8923-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

<span data-ttu-id="b8923-121">oraz</span><span class="sxs-lookup"><span data-stu-id="b8923-121">and</span></span>

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```