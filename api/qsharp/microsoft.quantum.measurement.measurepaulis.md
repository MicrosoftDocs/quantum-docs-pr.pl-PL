---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720345"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="49b49-102">MeasurePaulis, operacja</span><span class="sxs-lookup"><span data-stu-id="49b49-102">MeasurePaulis operation</span></span>

<span data-ttu-id="49b49-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="49b49-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="49b49-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49b49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49b49-105">Dana tablica operatorów wieloqubitowych Pauli, miara każdego przy użyciu określonego gadżetu pomiaru, a następnie zwraca tablicę wyników.</span><span class="sxs-lookup"><span data-stu-id="49b49-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="49b49-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="49b49-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="49b49-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="49b49-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="49b49-108">Tablica operatorów qubit Pauli, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="49b49-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="49b49-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="49b49-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="49b49-110">Zarejestruj się, w którym mają zostać dopasowane określone operatory.</span><span class="sxs-lookup"><span data-stu-id="49b49-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="49b49-111">Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="49b49-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="49b49-112">Operacja, która wykonuje pomiary danego operatora qubit.</span><span class="sxs-lookup"><span data-stu-id="49b49-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="49b49-113">Dane wyjściowe __: <Result> nieprawidłowe__ []</span><span class="sxs-lookup"><span data-stu-id="49b49-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="49b49-114">Tablica wyników uzyskanych od mierzenia każdego elementu `paulis` w `target` .</span><span class="sxs-lookup"><span data-stu-id="49b49-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>