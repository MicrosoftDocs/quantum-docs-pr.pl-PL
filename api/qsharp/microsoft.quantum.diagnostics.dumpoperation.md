---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829277"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="78a68-102">DumpOperation, operacja</span><span class="sxs-lookup"><span data-stu-id="78a68-102">DumpOperation operation</span></span>

<span data-ttu-id="78a68-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="78a68-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="78a68-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78a68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78a68-105">Po wykonaniu operacji program wyświetla diagnostykę operacji, które są dostępne dla bieżącego celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="78a68-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="78a68-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="78a68-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="78a68-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78a68-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78a68-108">Liczba qubits, w których dana operacja działa.</span><span class="sxs-lookup"><span data-stu-id="78a68-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="78a68-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="78a68-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="78a68-110">Operacja, która ma zostać zdiagnozowana.</span><span class="sxs-lookup"><span data-stu-id="78a68-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78a68-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78a68-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="78a68-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="78a68-112">Example</span></span>

<span data-ttu-id="78a68-113">Po uruchomieniu w obszarze docelowym symulatora Quantum Poniższy fragment kodu będzie wyprowadzał macierz $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned}.</span><span class="sxs-lookup"><span data-stu-id="78a68-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="78a68-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78a68-114">Remarks</span></span>

<span data-ttu-id="78a68-115">Wywołanie tej operacji nie ma zauważalnego efektu z poziomu Q #.</span><span class="sxs-lookup"><span data-stu-id="78a68-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="78a68-116">Dokładna Diagnostyka, która jest wyświetlana, jeśli istnieje, zależy od bieżącego celu wykonywania i środowiska edytora.</span><span class="sxs-lookup"><span data-stu-id="78a68-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="78a68-117">Na przykład, gdy jest używany w symulatorze Quantum o pełnym stanie, zostanie wyświetlona macierz jednostkowa użyta do reprezentowania `op` .</span><span class="sxs-lookup"><span data-stu-id="78a68-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="78a68-118">Należy pamiętać, że w przypadku korzystania z symulatorów, które dopuszczają niejednoznaczność globalną fazy (np. symulatora pełnego stanu), zwrócone reprezentacje mogą się różnić w zależności od globalnej fazy.</span><span class="sxs-lookup"><span data-stu-id="78a68-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="78a68-119">Podobnie porządkowanie macierzy wierszy i kolumn może różnić się w zależności od konwencji używanych przez każdy symulator obsługujący tę operację.</span><span class="sxs-lookup"><span data-stu-id="78a68-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>