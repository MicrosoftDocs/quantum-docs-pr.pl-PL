---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712973"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="1da62-102">AssertOperationsEqualInPlace, operacja</span><span class="sxs-lookup"><span data-stu-id="1da62-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="1da62-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1da62-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1da62-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1da62-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1da62-105">Dwie operacje, potwierdzają, że działają identycznie dla wszystkich stanów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="1da62-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="1da62-106">To potwierdzenie jest implementowane przez sprawdzenie działania operacji we wszystkich stanach formularza $V _0 \otimes... \otimes V_ {n-1} $, gdzie $V _k $ jest jednym z Stanów $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ i $ \ket{i} $ (+ 1 Eigenstate-Pauli-operator).</span><span class="sxs-lookup"><span data-stu-id="1da62-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="1da62-107">To potwierdzenie używa $n $ qubits i wymaga wielu wywołań operacji, które są porównywane.</span><span class="sxs-lookup"><span data-stu-id="1da62-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="1da62-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1da62-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1da62-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1da62-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1da62-110">Liczba qubits $n $, w których operacje `givenU` i `expectedU` działania.</span><span class="sxs-lookup"><span data-stu-id="1da62-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="1da62-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1da62-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1da62-112">Operacja na $n $ qubits do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="1da62-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="1da62-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1da62-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1da62-114">Operacja odwołania na $n $ qubits, która `givenU` ma zostać porównana z.</span><span class="sxs-lookup"><span data-stu-id="1da62-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1da62-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1da62-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="1da62-116">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="1da62-116">References</span></span>

<span data-ttu-id="1da62-117">Podstawa States $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ i $ \ket{i} $ to Chuang-Nielsen, opisana w [ *i. L. Czuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="1da62-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="1da62-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1da62-118">See Also</span></span>

- [<span data-ttu-id="1da62-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="1da62-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)