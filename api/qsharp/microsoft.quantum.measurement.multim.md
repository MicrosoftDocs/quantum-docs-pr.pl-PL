---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711041"
---
# <a name="multim-operation"></a><span data-ttu-id="17247-102">MultiM, operacja</span><span class="sxs-lookup"><span data-stu-id="17247-102">MultiM operation</span></span>

<span data-ttu-id="17247-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="17247-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="17247-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17247-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17247-105">Mierzy każdy qubit w danej tablicy w standardowej bazie.</span><span class="sxs-lookup"><span data-stu-id="17247-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="17247-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="17247-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="17247-107">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="17247-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="17247-108">Tablica qubits do zmierzenia.</span><span class="sxs-lookup"><span data-stu-id="17247-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="17247-109">Dane wyjściowe __: <Result> nieprawidłowe__ []</span><span class="sxs-lookup"><span data-stu-id="17247-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="17247-110">Tablica wyników pomiarów.</span><span class="sxs-lookup"><span data-stu-id="17247-110">An array of measurement results.</span></span>