---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202060"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="2f1cd-102">DumpOperation, operacja</span><span class="sxs-lookup"><span data-stu-id="2f1cd-102">DumpOperation operation</span></span>

<span data-ttu-id="2f1cd-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2f1cd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2f1cd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f1cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f1cd-105">Po wykonaniu operacji program wyświetla diagnostykę operacji, które są dostępne dla bieżącego celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="2f1cd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2f1cd-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2f1cd-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f1cd-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f1cd-108">Liczba qubits, w których dana operacja działa.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="2f1cd-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="2f1cd-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2f1cd-110">Operacja, która ma zostać zdiagnozowana.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f1cd-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f1cd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2f1cd-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2f1cd-112">Remarks</span></span>

<span data-ttu-id="2f1cd-113">Wywołanie tej operacji nie ma zauważalnego efektu z poziomu Q #.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="2f1cd-114">Dokładna Diagnostyka, która jest wyświetlana, jeśli istnieje, zależy od bieżącego celu wykonywania i środowiska edytora.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="2f1cd-115">Na przykład, gdy jest używany w symulatorze Quantum o pełnym stanie, zostanie wyświetlona macierz jednostkowa użyta do reprezentowania `op` .</span><span class="sxs-lookup"><span data-stu-id="2f1cd-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="2f1cd-116">Należy pamiętać, że w przypadku korzystania z symulatorów, które dopuszczają niejednoznaczność globalną fazy (np. symulatora pełnego stanu), zwrócone reprezentacje mogą się różnić w zależności od globalnej fazy.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="2f1cd-117">Podobnie porządkowanie macierzy wierszy i kolumn może różnić się w zależności od konwencji używanych przez każdy symulator obsługujący tę operację.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>