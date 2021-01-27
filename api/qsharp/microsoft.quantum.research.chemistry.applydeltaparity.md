---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851111"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="c035c-102">ApplyDeltaParity, operacja</span><span class="sxs-lookup"><span data-stu-id="c035c-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="c035c-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c035c-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c035c-104">Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c035c-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="c035c-105">Oblicza różnicę między poprzednim PQRS... warunki i następne PQRS... mandat.</span><span class="sxs-lookup"><span data-stu-id="c035c-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="c035c-106">Różnica jest obliczana na pomocniczej qubit.</span><span class="sxs-lookup"><span data-stu-id="c035c-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c035c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c035c-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="c035c-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c035c-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c035c-109">Lista indeksów z poprzednią PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="c035c-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="c035c-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c035c-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c035c-111">Lista indeksów do następnego PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="c035c-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="c035c-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c035c-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c035c-113">Pomocniczy qubit, na którym są przechowywane wyniki obliczeń parzystości.</span><span class="sxs-lookup"><span data-stu-id="c035c-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c035c-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c035c-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c035c-115">Qubit na wszystkie PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="c035c-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c035c-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c035c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c035c-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c035c-117">Remarks</span></span>

<span data-ttu-id="c035c-118">Przyjęto założenie, że indeksy P < Q < R < S <... zarówno prevPQ, jak i nextPQ.</span><span class="sxs-lookup"><span data-stu-id="c035c-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>