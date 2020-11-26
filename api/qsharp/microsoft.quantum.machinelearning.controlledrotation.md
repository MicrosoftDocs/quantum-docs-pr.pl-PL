---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196569"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="f9f77-102">ControlledRotation typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="f9f77-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="f9f77-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9f77-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f9f77-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f9f77-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f9f77-105">Opisuje ukierunkowane rotacje w warunkach jego celu i indeksów kontroli, osi obrotu i indeksu do wektora parametru modelu.</span><span class="sxs-lookup"><span data-stu-id="f9f77-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="f9f77-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="f9f77-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="f9f77-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9f77-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9f77-108">Indeks qubit docelowego dla tego kontrolowanego obrotu.</span><span class="sxs-lookup"><span data-stu-id="f9f77-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="f9f77-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f9f77-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f9f77-110">Tablica indeksów qubit dla tego obrotu.</span><span class="sxs-lookup"><span data-stu-id="f9f77-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="f9f77-111">Oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f9f77-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f9f77-112">Oś dla tego obrotu.</span><span class="sxs-lookup"><span data-stu-id="f9f77-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="f9f77-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9f77-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9f77-114">Indeks do wektora parametru modelu opisującego kąt tego obrotu.</span><span class="sxs-lookup"><span data-stu-id="f9f77-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9f77-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9f77-115">Remarks</span></span>

<span data-ttu-id="f9f77-116">Obrót niekontrolowany może być reprezentowany przez ustawienie `ControlIndices` do pustej tablicy indeksów `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="f9f77-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>