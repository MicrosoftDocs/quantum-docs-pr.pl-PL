---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229209"
---
# <a name="inttopauli-function"></a><span data-ttu-id="f5f0d-102">IntToPauli, funkcja</span><span class="sxs-lookup"><span data-stu-id="f5f0d-102">IntToPauli function</span></span>

<span data-ttu-id="f5f0d-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f5f0d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f5f0d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5f0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5f0d-105">Konwertuje liczbę całkowitą na operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="f5f0d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f5f0d-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="f5f0d-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5f0d-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5f0d-108">Liczba całkowita z zakresu `0..3` do przekonwertowania na operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="f5f0d-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f5f0d-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f5f0d-110">`Pauli`Operator określony przez `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="f5f0d-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>