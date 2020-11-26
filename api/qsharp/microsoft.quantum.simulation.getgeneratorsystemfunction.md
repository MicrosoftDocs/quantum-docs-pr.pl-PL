---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 28e3c12d0ae0b08fc368c25eeb6f38d2834ca912
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229311"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="3a56c-102">GetGeneratorSystemFunction, funkcja</span><span class="sxs-lookup"><span data-stu-id="3a56c-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="3a56c-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3a56c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3a56c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a56c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a56c-105">Pobiera `GeneratorIndex` funkcję w `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="3a56c-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="3a56c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3a56c-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="3a56c-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3a56c-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3a56c-108">`GeneratorSystem`Interesu.</span><span class="sxs-lookup"><span data-stu-id="3a56c-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="3a56c-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3a56c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3a56c-110">Funkcja, która indeksuje każdy `GeneratorIndex` termin w hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="3a56c-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a56c-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a56c-111">See Also</span></span>

- [<span data-ttu-id="3a56c-112">Microsoft. Quantum. Symulacja. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="3a56c-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="3a56c-113">Microsoft. Quantum. Symulacja. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3a56c-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)