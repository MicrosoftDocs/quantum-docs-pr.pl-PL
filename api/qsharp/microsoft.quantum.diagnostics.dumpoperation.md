---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712861"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="1a88f-102">DumpOperation, operacja</span><span class="sxs-lookup"><span data-stu-id="1a88f-102">DumpOperation operation</span></span>

<span data-ttu-id="1a88f-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1a88f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1a88f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a88f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a88f-105">Po wykonaniu operacji program wyświetla diagnostykę operacji, które są dostępne dla bieżącego celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="1a88f-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="1a88f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1a88f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1a88f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a88f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a88f-108">Liczba qubits, w których dana operacja działa.</span><span class="sxs-lookup"><span data-stu-id="1a88f-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="1a88f-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a88f-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1a88f-110">Operacja, która ma zostać zdiagnozowana.</span><span class="sxs-lookup"><span data-stu-id="1a88f-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1a88f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a88f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a88f-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1a88f-112">Remarks</span></span>

<span data-ttu-id="1a88f-113">Wywołanie tej operacji nie ma zauważalnego efektu z poziomu Q #.</span><span class="sxs-lookup"><span data-stu-id="1a88f-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="1a88f-114">Dokładna Diagnostyka, która jest wyświetlana, jeśli istnieje, zależy od bieżącego celu wykonywania i środowiska edytora.</span><span class="sxs-lookup"><span data-stu-id="1a88f-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="1a88f-115">Na przykład, gdy jest używany w symulatorze Quantum o pełnym stanie, zostanie wyświetlona macierz jednostkowa użyta do reprezentowania `op` .</span><span class="sxs-lookup"><span data-stu-id="1a88f-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="1a88f-116">Należy pamiętać, że w przypadku korzystania z symulatorów, które dopuszczają niejednoznaczność globalną fazy (np. symulatora pełnego stanu), zwrócone reprezentacje mogą się różnić w zależności od globalnej fazy.</span><span class="sxs-lookup"><span data-stu-id="1a88f-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="1a88f-117">Podobnie porządkowanie macierzy wierszy i kolumn może różnić się w zależności od konwencji używanych przez każdy symulator obsługujący tę operację.</span><span class="sxs-lookup"><span data-stu-id="1a88f-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>