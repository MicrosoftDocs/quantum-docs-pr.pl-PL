---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211937"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="90f1f-102">CyclicEntanglingLayer, funkcja</span><span class="sxs-lookup"><span data-stu-id="90f1f-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="90f1f-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="90f1f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="90f1f-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="90f1f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="90f1f-105">Zwraca tablicę z pojedynczo kontrolowanymi obrotami wzdłuż danej osi, ułożone cyklicznie w rejestrze qubits i sparametryzowane według odrębnych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="90f1f-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="90f1f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90f1f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="90f1f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90f1f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90f1f-108">Liczba qubits działań na podstawie danej warstwy.</span><span class="sxs-lookup"><span data-stu-id="90f1f-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="90f1f-109">oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="90f1f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="90f1f-110">Oś obrotu dla każdego obrotu w danej warstwie.</span><span class="sxs-lookup"><span data-stu-id="90f1f-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="90f1f-111">Krok: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90f1f-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90f1f-112">Rozdzielenie między elementami docelowymi a kontrolkami kontroli dla każdego obrotu.</span><span class="sxs-lookup"><span data-stu-id="90f1f-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="90f1f-113">Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="90f1f-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="90f1f-114">Tablica przekreśleń z dwoma qubitami, które są rozmieszczone cyklicznie przez rejestr `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="90f1f-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>