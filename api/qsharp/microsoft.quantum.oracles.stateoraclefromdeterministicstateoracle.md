---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724219"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="0bd40-102">StateOracleFromDeterministicStateOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="0bd40-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="0bd40-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0bd40-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0bd40-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bd40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bd40-105">Konwertuje Oracle typu `DeterministicStateOracle` na `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="0bd40-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="0bd40-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0bd40-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="0bd40-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="0bd40-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="0bd40-108">Przygotowanie stanu $A $ typu programu Oracle `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="0bd40-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="0bd40-109">Wynik: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="0bd40-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="0bd40-110">To samo przygotowanie stanu $A $, ale teraz typu `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="0bd40-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="0bd40-111">Należy zauważyć, że indeks flagi w tym `StateOracle` jest zmienną fikcyjną i nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="0bd40-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bd40-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0bd40-112">See Also</span></span>

- [<span data-ttu-id="0bd40-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="0bd40-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="0bd40-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="0bd40-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)