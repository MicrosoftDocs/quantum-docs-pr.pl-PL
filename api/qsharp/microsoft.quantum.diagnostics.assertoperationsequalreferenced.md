---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712959"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="0ed13-102">AssertOperationsEqualReferenced, operacja</span><span class="sxs-lookup"><span data-stu-id="0ed13-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="0ed13-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0ed13-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0ed13-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ed13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ed13-105">Dwie operacje, potwierdzają, że działają identycznie dla wszystkich stanów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="0ed13-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="0ed13-106">To potwierdzenie jest implementowane za pomocą Choi – Jamiołkowski isomorphism, aby ograniczyć potwierdzenie do jednego z potwierdzeń stanu qubit na dwóch rejestrach Entangled.</span><span class="sxs-lookup"><span data-stu-id="0ed13-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="0ed13-107">W rezultacie ta operacja wymaga tylko jednego wywołania dla każdej testowanej operacji, ale wymaga dwukrotnego przydzielenia qubits.</span><span class="sxs-lookup"><span data-stu-id="0ed13-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="0ed13-108">To potwierdzenie może służyć do upewnienia się, że na przykład, że zoptymalizowana wersja operacji działa identycznie z implementacją algorytmie, lub że operacja, która działa w zakresie danych wejściowych innych niż Quantum, zgadza się ze znanymi przypadkami.</span><span class="sxs-lookup"><span data-stu-id="0ed13-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="0ed13-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0ed13-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="0ed13-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ed13-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ed13-111">Liczba qubits do przekazania do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="0ed13-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="0ed13-112">rzeczywista: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0ed13-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0ed13-113">Operacja do przetestowania.</span><span class="sxs-lookup"><span data-stu-id="0ed13-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="0ed13-114">Oczekiwano: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ed13-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0ed13-115">Operacja definiująca oczekiwane zachowanie testowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="0ed13-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ed13-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ed13-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0ed13-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ed13-117">Remarks</span></span>

<span data-ttu-id="0ed13-118">Ta operacja wymaga, aby model operacji modelował oczekiwane zachowanie, tak aby można było wykonać operację odwrotną dla samego rejestru docelowego.</span><span class="sxs-lookup"><span data-stu-id="0ed13-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="0ed13-119">Jeden z nich może określać transpozycję operacji, która powoduje, że to wymaganie, ale operacja transpozycji nie jest ogólnie obsługiwana w przypadku dowolnych operacji Quantum i w tym przypadku nie jest uwzględniona w tym miejscu jako opcja.</span><span class="sxs-lookup"><span data-stu-id="0ed13-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>