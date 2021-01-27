---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848003"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="b4460-102">PauliBlockEncoding, funkcja</span><span class="sxs-lookup"><span data-stu-id="b4460-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="b4460-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b4460-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b4460-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4460-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4460-105">Tworzy moduł kodowania bloku dla hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="b4460-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="b4460-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ jest opisywany przez sumę Pauliych warunków $P _j $, każdy z rzeczywistym czynnikiem $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="b4460-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="b4460-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b4460-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b4460-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b4460-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b4460-109">A `GeneratorSystem` , który opisuje $H $ jako sumę Pauli warunków</span><span class="sxs-lookup"><span data-stu-id="b4460-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="b4460-110">Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="b4460-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="b4460-111">Pierwszy parametr</span><span class="sxs-lookup"><span data-stu-id="b4460-111">First parameter</span></span>

<span data-ttu-id="b4460-112">Jedna z norm współczynników $ \Alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="b4460-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="b4460-113">Drugi parametr</span><span class="sxs-lookup"><span data-stu-id="b4460-113">Second parameter</span></span>

<span data-ttu-id="b4460-114">`BlockEncodingReflection`Jednostkowa $U $ Hamiltonian $H $.</span><span class="sxs-lookup"><span data-stu-id="b4460-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="b4460-115">Ponieważ ta jednostka jest taka sama jak $U ^ 2 = I $, jest również odbiciem.</span><span class="sxs-lookup"><span data-stu-id="b4460-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4460-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b4460-116">Remarks</span></span>

<span data-ttu-id="b4460-117">Jest on uzyskiwany przez przygotowanie i cofnięcie przygotowania stanu $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ i skonstruowanie kontrolowanego jednostkowo jednostki <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> i <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="b4460-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>