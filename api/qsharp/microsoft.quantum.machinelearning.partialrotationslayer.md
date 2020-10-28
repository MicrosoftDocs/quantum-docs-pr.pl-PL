---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722432"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="f9c57-102">PartialRotationsLayer, funkcja</span><span class="sxs-lookup"><span data-stu-id="f9c57-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="f9c57-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9c57-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f9c57-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9c57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9c57-105">Zwraca tablicę obrotów z pojedynczą qubitą wzdłuż danej osi, sparametryzowane według odrębnych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="f9c57-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="f9c57-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f9c57-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="f9c57-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f9c57-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f9c57-108">Indeksy dla qubits mają być używane jako elementy docelowe dla każdego obrotu.</span><span class="sxs-lookup"><span data-stu-id="f9c57-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="f9c57-109">oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f9c57-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f9c57-110">Oś obrotu dla każdego obrotu w danej warstwie.</span><span class="sxs-lookup"><span data-stu-id="f9c57-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="f9c57-111">Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f9c57-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f9c57-112">Tablica kontrolowanych obrotów o podaną oś, jedna na każdej z `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="f9c57-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>