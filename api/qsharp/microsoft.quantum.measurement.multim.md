---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226999"
---
# <a name="multim-operation"></a><span data-ttu-id="8fd0b-102">MultiM, operacja</span><span class="sxs-lookup"><span data-stu-id="8fd0b-102">MultiM operation</span></span>

<span data-ttu-id="8fd0b-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8fd0b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8fd0b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8fd0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8fd0b-105">Mierzy każdy qubit w danej tablicy w standardowej bazie.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="8fd0b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8fd0b-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="8fd0b-107">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8fd0b-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8fd0b-108">Tablica qubits do zmierzenia.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8fd0b-109">Dane wyjściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="8fd0b-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="8fd0b-110">Tablica wyników pomiarów.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-110">An array of measurement results.</span></span>