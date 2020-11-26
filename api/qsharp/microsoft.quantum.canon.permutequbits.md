---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205610"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="2f506-102">PermuteQubits, operacja</span><span class="sxs-lookup"><span data-stu-id="2f506-102">PermuteQubits operation</span></span>

<span data-ttu-id="2f506-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f506-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f506-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f506-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f506-105">Permutes qubits przy użyciu operacji ZAMIANy.</span><span class="sxs-lookup"><span data-stu-id="2f506-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2f506-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2f506-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="2f506-107">Porządkowanie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f506-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f506-108">Opisuje nową kolejność qubits, gdzie qubit w indeksie, teraz będzie w kolejności [i].</span><span class="sxs-lookup"><span data-stu-id="2f506-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="2f506-109">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2f506-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2f506-110">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="2f506-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f506-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f506-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

