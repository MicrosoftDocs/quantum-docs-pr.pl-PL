---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844340"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="fc181-102">IdentityGeneratorIndex, funkcja</span><span class="sxs-lookup"><span data-stu-id="fc181-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="fc181-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fc181-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fc181-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc181-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc181-105">Zwraca indeks generatora spójny z zerem hamiltonian, `H = 0` który odnosi się do operacji ewolucji tożsamości.</span><span class="sxs-lookup"><span data-stu-id="fc181-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="fc181-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fc181-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="fc181-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc181-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc181-108">To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.simulation.generatorsystem> typem zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fc181-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="fc181-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fc181-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fc181-110">Indeks generatora reprezentujący ewolucję w hamiltonian $H = $0.</span><span class="sxs-lookup"><span data-stu-id="fc181-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>