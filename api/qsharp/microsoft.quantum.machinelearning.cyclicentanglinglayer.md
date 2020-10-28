---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720513"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="85de8-102">CyclicEntanglingLayer, funkcja</span><span class="sxs-lookup"><span data-stu-id="85de8-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="85de8-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="85de8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="85de8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="85de8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="85de8-105">Zwraca tablicę z pojedynczo kontrolowanymi obrotami wzdłuż danej osi, ułożone cyklicznie w rejestrze qubits i sparametryzowane według odrębnych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="85de8-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="85de8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="85de8-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="85de8-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85de8-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="85de8-108">Liczba qubits działań na podstawie danej warstwy.</span><span class="sxs-lookup"><span data-stu-id="85de8-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="85de8-109">oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="85de8-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="85de8-110">Oś obrotu dla każdego obrotu w danej warstwie.</span><span class="sxs-lookup"><span data-stu-id="85de8-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="85de8-111">Krok: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85de8-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="85de8-112">Rozdzielenie między elementami docelowymi a kontrolkami kontroli dla każdego obrotu.</span><span class="sxs-lookup"><span data-stu-id="85de8-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="85de8-113">Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="85de8-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="85de8-114">Tablica przekreśleń z dwoma qubitami, które są rozmieszczone cyklicznie przez rejestr `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="85de8-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>