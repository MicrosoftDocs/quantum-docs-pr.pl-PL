---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720216"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="78a7e-102">PauliBlockEncoding, funkcja</span><span class="sxs-lookup"><span data-stu-id="78a7e-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="78a7e-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="78a7e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="78a7e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78a7e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78a7e-105">Tworzy moduł kodowania bloku dla hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="78a7e-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="78a7e-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ jest opisywany przez sumę Pauliych warunków $P _j $, każdy z rzeczywistym czynnikiem $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="78a7e-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="78a7e-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="78a7e-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="78a7e-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="78a7e-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="78a7e-109">A `GeneratorSystem` , który opisuje $H $ jako sumę Pauli warunków</span><span class="sxs-lookup"><span data-stu-id="78a7e-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="78a7e-110">Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="78a7e-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="78a7e-111">Pierwszy parametr</span><span class="sxs-lookup"><span data-stu-id="78a7e-111">First parameter</span></span>

<span data-ttu-id="78a7e-112">Jedna z norm współczynników $ \Alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="78a7e-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="78a7e-113">Drugi parametr</span><span class="sxs-lookup"><span data-stu-id="78a7e-113">Second parameter</span></span>

<span data-ttu-id="78a7e-114">`BlockEncodingReflection`Jednostkowa $U $ Hamiltonian $H $.</span><span class="sxs-lookup"><span data-stu-id="78a7e-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="78a7e-115">Ponieważ ta jednostka jest taka sama jak $U ^ 2 = I $, jest również odbiciem.</span><span class="sxs-lookup"><span data-stu-id="78a7e-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="78a7e-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78a7e-116">Remarks</span></span>

<span data-ttu-id="78a7e-117">Jest on uzyskiwany przez przygotowanie i cofnięcie przygotowania stanu $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ i skonstruowanie kontrolowanego jednostkowo jednostki <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> i <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="78a7e-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>