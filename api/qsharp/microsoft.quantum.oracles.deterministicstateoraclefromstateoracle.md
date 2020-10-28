---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724252"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="c03fd-102">DeterministicStateOracleFromStateOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="c03fd-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="c03fd-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c03fd-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c03fd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c03fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c03fd-105">Konwertuje Oracle typu `StateOracle` na `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c03fd-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="c03fd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c03fd-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="c03fd-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c03fd-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c03fd-108">Indeks qubita flagi `stateOracle` $A $, która jawnie działa w dwóch rejestrach: flaga $f $ i system $s $, np. $A \ket {0} \_ f\ket {\ psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="c03fd-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="c03fd-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c03fd-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c03fd-110">Przygotowanie stanu $A $ typu programu Oracle `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c03fd-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="c03fd-111">Wynik: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="c03fd-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="c03fd-112">Ten sam zbiór danych o stanie Oracle $A $, ale teraz `DeterministicStateOracle` , działa na rejestrze, gdzie $a, s $ nie jest już jawnie odrębny, np.  $A \ket{0\psi} \_ {AS} $.</span><span class="sxs-lookup"><span data-stu-id="c03fd-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="c03fd-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c03fd-113">See Also</span></span>

- [<span data-ttu-id="c03fd-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="c03fd-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="c03fd-115">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="c03fd-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)