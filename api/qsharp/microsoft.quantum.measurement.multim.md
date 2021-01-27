---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857010"
---
# <a name="multim-operation"></a><span data-ttu-id="34b05-102">MultiM, operacja</span><span class="sxs-lookup"><span data-stu-id="34b05-102">MultiM operation</span></span>

<span data-ttu-id="34b05-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="34b05-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="34b05-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34b05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34b05-105">Mierzy każdy qubit w danej tablicy w standardowej bazie.</span><span class="sxs-lookup"><span data-stu-id="34b05-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="34b05-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="34b05-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="34b05-107">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="34b05-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="34b05-108">Tablica qubits do zmierzenia.</span><span class="sxs-lookup"><span data-stu-id="34b05-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="34b05-109">Dane wyjściowe __: <Result> nieprawidłowe__[]</span><span class="sxs-lookup"><span data-stu-id="34b05-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="34b05-110">Tablica wyników pomiarów.</span><span class="sxs-lookup"><span data-stu-id="34b05-110">An array of measurement results.</span></span>