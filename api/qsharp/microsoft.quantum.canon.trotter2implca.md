---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715311"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="ed44c-102">Trotter2ImplCA, operacja</span><span class="sxs-lookup"><span data-stu-id="ed44c-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="ed44c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ed44c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ed44c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed44c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed44c-105">Implementacja integratora Trotter — Suzuki.</span><span class="sxs-lookup"><span data-stu-id="ed44c-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="ed44c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ed44c-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="ed44c-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed44c-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed44c-108">Liczba operacji do rozdzielenia na etapy czasu.</span><span class="sxs-lookup"><span data-stu-id="ed44c-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="ed44c-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="ed44c-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ed44c-110">Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) i rejestr Quantum (typ `'T` ) dla dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="ed44c-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ed44c-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed44c-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed44c-112">Mnożnik na rozmiar każdego kroku symulacji.</span><span class="sxs-lookup"><span data-stu-id="ed44c-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="ed44c-113">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="ed44c-113">target : 'T</span></span>

<span data-ttu-id="ed44c-114">Rejestr Quantum, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="ed44c-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed44c-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed44c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ed44c-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ed44c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ed44c-117">'C</span><span class="sxs-lookup"><span data-stu-id="ed44c-117">'T</span></span>

<span data-ttu-id="ed44c-118">Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="ed44c-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>