---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722180"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="37dba-102">ReflectionOracleFromDeterministicStateOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="37dba-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="37dba-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="37dba-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="37dba-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37dba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37dba-105">Tworzy odbicie dotyczące danego stanu z bazy danych Oracle.</span><span class="sxs-lookup"><span data-stu-id="37dba-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="37dba-106">Opis</span><span class="sxs-lookup"><span data-stu-id="37dba-106">Description</span></span>

<span data-ttu-id="37dba-107">Uwzględniając, że program Oracle State preparat jest reprezentowany przez macierz jednostkową $O $, wynikiem tej funkcji jest Oracle, która stosuje odbicie wokół stanu $ \ket{\psi} $ przygotowanego przez Oracle $O $; oznacza to, że stan $ \ket{\psi} $ taki, który $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="37dba-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="37dba-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="37dba-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="37dba-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="37dba-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="37dba-110">Oracle, który przygotowuje kopie stanu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="37dba-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="37dba-111">Wynik: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="37dba-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="37dba-112">Oracle, który odzwierciedla informacje o stanie $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="37dba-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="37dba-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37dba-113">See Also</span></span>

- [<span data-ttu-id="37dba-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="37dba-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="37dba-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="37dba-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)