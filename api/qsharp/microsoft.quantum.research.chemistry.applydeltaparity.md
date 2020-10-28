---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723981"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="2a86f-102">ApplyDeltaParity, operacja</span><span class="sxs-lookup"><span data-stu-id="2a86f-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="2a86f-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2a86f-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="2a86f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a86f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a86f-105">Oblicza różnicę między poprzednim PQRS... warunki i następne PQRS... mandat.</span><span class="sxs-lookup"><span data-stu-id="2a86f-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="2a86f-106">Różnica jest obliczana na pomocniczej qubit.</span><span class="sxs-lookup"><span data-stu-id="2a86f-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2a86f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2a86f-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="2a86f-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a86f-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a86f-109">Lista indeksów z poprzednią PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="2a86f-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="2a86f-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a86f-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a86f-111">Lista indeksów do następnego PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="2a86f-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="2a86f-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2a86f-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2a86f-113">Pomocniczy qubit, na którym są przechowywane wyniki obliczeń parzystości.</span><span class="sxs-lookup"><span data-stu-id="2a86f-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2a86f-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2a86f-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2a86f-115">Qubit na wszystkie PQRS... odsetk.</span><span class="sxs-lookup"><span data-stu-id="2a86f-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a86f-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a86f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2a86f-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2a86f-117">Remarks</span></span>

<span data-ttu-id="2a86f-118">Przyjęto założenie, że indeksy P < Q < R < S <... zarówno prevPQ, jak i nextPQ.</span><span class="sxs-lookup"><span data-stu-id="2a86f-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>