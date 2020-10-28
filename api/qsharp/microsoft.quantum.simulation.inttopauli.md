---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724849"
---
# <a name="inttopauli-function"></a><span data-ttu-id="429fc-102">IntToPauli, funkcja</span><span class="sxs-lookup"><span data-stu-id="429fc-102">IntToPauli function</span></span>

<span data-ttu-id="429fc-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="429fc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="429fc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="429fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="429fc-105">Konwertuje liczbę całkowitą na operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="429fc-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="429fc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="429fc-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="429fc-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="429fc-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="429fc-108">Liczba całkowita z zakresu `0..3` do przekonwertowania na operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="429fc-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="429fc-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="429fc-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="429fc-110">`Pauli`Operator określony przez `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="429fc-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>