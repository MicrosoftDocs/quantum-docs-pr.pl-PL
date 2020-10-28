---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720324"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="8856b-102">MeasureWithScratch, operacja</span><span class="sxs-lookup"><span data-stu-id="8856b-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="8856b-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8856b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8856b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8856b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8856b-105">Mierzy dany operator Pauli za pomocą jawnego qubitu do przeprowadzenia pomiaru.</span><span class="sxs-lookup"><span data-stu-id="8856b-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="8856b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8856b-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="8856b-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8856b-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8856b-108">Operator qubit Pauli określony jako tablica operatorów z pojedynczą qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="8856b-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8856b-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8856b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8856b-110">Qubit rejestr do zmierzenia.</span><span class="sxs-lookup"><span data-stu-id="8856b-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8856b-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="8856b-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8856b-112">Wynik pomiaru danego operatora Pauli w `target` rejestrze.</span><span class="sxs-lookup"><span data-stu-id="8856b-112">The result of measuring the given Pauli operator on the `target` register.</span></span>