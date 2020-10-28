---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723468"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="07cd7-102">LocalRotationsLayer, funkcja</span><span class="sxs-lookup"><span data-stu-id="07cd7-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="07cd7-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="07cd7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="07cd7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07cd7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07cd7-105">Zwraca tablicę niekontrolowanych (qubit) rotacji wzdłuż danej osi, z jednym obrotem dla każdego qubit w rejestrze, sparametryzowane według odrębnych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="07cd7-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="07cd7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="07cd7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="07cd7-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07cd7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07cd7-108">Liczba qubits działań na podstawie danej warstwy.</span><span class="sxs-lookup"><span data-stu-id="07cd7-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="07cd7-109">oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="07cd7-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="07cd7-110">Oś obrotu dla każdego obrotu w danej warstwie.</span><span class="sxs-lookup"><span data-stu-id="07cd7-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="07cd7-111">Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="07cd7-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="07cd7-112">Tablica kontrolowanych obrotów o podaną oś, jedna na każdej z `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="07cd7-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>