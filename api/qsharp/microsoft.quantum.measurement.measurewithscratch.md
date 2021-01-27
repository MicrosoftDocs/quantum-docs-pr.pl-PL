---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854656"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="d04b8-102">MeasureWithScratch, operacja</span><span class="sxs-lookup"><span data-stu-id="d04b8-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="d04b8-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d04b8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d04b8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d04b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d04b8-105">Mierzy dany operator Pauli za pomocą jawnego qubitu do przeprowadzenia pomiaru.</span><span class="sxs-lookup"><span data-stu-id="d04b8-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="d04b8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d04b8-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="d04b8-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d04b8-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d04b8-108">Operator qubit Pauli określony jako tablica operatorów z pojedynczą qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="d04b8-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d04b8-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d04b8-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d04b8-110">Qubit rejestr do zmierzenia.</span><span class="sxs-lookup"><span data-stu-id="d04b8-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d04b8-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="d04b8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d04b8-112">Wynik pomiaru danego operatora Pauli w `target` rejestrze.</span><span class="sxs-lookup"><span data-stu-id="d04b8-112">The result of measuring the given Pauli operator on the `target` register.</span></span>