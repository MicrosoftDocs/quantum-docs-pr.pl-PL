---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853766"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="2b505-102">MeasurePaulis, operacja</span><span class="sxs-lookup"><span data-stu-id="2b505-102">MeasurePaulis operation</span></span>

<span data-ttu-id="2b505-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2b505-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2b505-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b505-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b505-105">Dana tablica operatorów wieloqubitowych Pauli, miara każdego przy użyciu określonego gadżetu pomiaru, a następnie zwraca tablicę wyników.</span><span class="sxs-lookup"><span data-stu-id="2b505-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="2b505-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2b505-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="2b505-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="2b505-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="2b505-108">Tablica operatorów qubit Pauli, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="2b505-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2b505-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b505-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b505-110">Zarejestruj się, w którym mają zostać dopasowane określone operatory.</span><span class="sxs-lookup"><span data-stu-id="2b505-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="2b505-111">Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="2b505-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="2b505-112">Operacja, która wykonuje pomiary danego operatora qubit.</span><span class="sxs-lookup"><span data-stu-id="2b505-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2b505-113">Dane wyjściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="2b505-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="2b505-114">Tablica wyników uzyskanych od mierzenia każdego elementu `paulis` w `target` .</span><span class="sxs-lookup"><span data-stu-id="2b505-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>