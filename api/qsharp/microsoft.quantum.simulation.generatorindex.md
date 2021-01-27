---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858384"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="b9982-102">GeneratorIndex typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b9982-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="b9982-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b9982-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b9982-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9982-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9982-105">Reprezentuje pojedynczy termin pierwotny w zestawie wszystkich generatorów dynamicznych, np. operatorów hermitian, dla których istnieje mapa z tego generatora do czasu ewolucji przez ten generator, za pośrednictwem `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="b9982-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="b9982-106">Pierwszy element (int [], Double []) jest indeksem, który jest pojedynczym terminem — na przykład Pauli ciąg XXY z współczynnikem 0,5 będzie indeksowany przez ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="b9982-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="b9982-107">Alternatywnie, Hamiltonians sparametryzowane przez zmienną ciągłą, taką jak X cos φ + Y Sin φ, może być reprezentowane przez ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="b9982-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="b9982-108">Drugi element indeksuje podsystem, na którym działa Generator.</span><span class="sxs-lookup"><span data-stu-id="b9982-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="b9982-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="b9982-109">Example</span></span>

<span data-ttu-id="b9982-110">Przy użyciu  <xref:microsoft.quantum.simulation.paulievolutionset> , operator $ \pi X_2 X_5 Y_9 $ jest reprezentowany jako:</span><span class="sxs-lookup"><span data-stu-id="b9982-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="b9982-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b9982-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b9982-112">Interpretacja elementu `GeneratorIndex` nie jest zdefiniowana, z wyjątkiem odwołania do określonego zestawu generatorów.</span><span class="sxs-lookup"><span data-stu-id="b9982-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9982-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9982-113">See Also</span></span>

- [<span data-ttu-id="b9982-114">Microsoft. Quantum. Symulacja. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="b9982-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="b9982-115">Microsoft. Quantum. Symulacja. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="b9982-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)