---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842527"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="a3942-102">ReflectionOracleFromDeterministicStateOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="a3942-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="a3942-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a3942-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a3942-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3942-105">Tworzy odbicie dotyczące danego stanu z bazy danych Oracle.</span><span class="sxs-lookup"><span data-stu-id="a3942-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="a3942-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a3942-106">Description</span></span>

<span data-ttu-id="a3942-107">Uwzględniając, że program Oracle State preparat jest reprezentowany przez macierz jednostkową $O $, wynikiem tej funkcji jest Oracle, która stosuje odbicie wokół stanu $ \ket{\psi} $ przygotowanego przez Oracle $O $; oznacza to, że stan $ \ket{\psi} $ taki, który $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="a3942-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="a3942-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a3942-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="a3942-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="a3942-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="a3942-110">Oracle, który przygotowuje kopie stanu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="a3942-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="a3942-111">Wynik: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a3942-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a3942-112">Oracle, który odzwierciedla informacje o stanie $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="a3942-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3942-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3942-113">See Also</span></span>

- [<span data-ttu-id="a3942-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="a3942-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="a3942-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="a3942-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)