---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724541"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="6f66e-102">IdentityGeneratorIndex, funkcja</span><span class="sxs-lookup"><span data-stu-id="6f66e-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="6f66e-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6f66e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6f66e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f66e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f66e-105">Zwraca indeks generatora spójny z zerem hamiltonian, `H = 0` który odnosi się do operacji ewolucji tożsamości.</span><span class="sxs-lookup"><span data-stu-id="6f66e-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="6f66e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6f66e-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="6f66e-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f66e-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f66e-108">To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.simulation.generatorsystem> typem zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6f66e-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="6f66e-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6f66e-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6f66e-110">Indeks generatora reprezentujący ewolucję w hamiltonian $H = $0.</span><span class="sxs-lookup"><span data-stu-id="6f66e-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>