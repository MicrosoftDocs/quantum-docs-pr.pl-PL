---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funkcja _IdentityTimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710691"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="38726-102">Funkcja _IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="38726-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="38726-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="38726-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="38726-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38726-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38726-105">Zwraca System generatora spójny z hamiltonian `H(s) = 0` , gdzie `s` jest parametrem harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="38726-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="38726-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="38726-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="38726-107">Harmonogram: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38726-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38726-108">To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.canon.timedependentgeneratorsystem> typem zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="38726-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="38726-109">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="38726-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="38726-110">System generatora reprezentujący ewolucję w hamiltonian $H (s) = $0 dla wszystkich $s $.</span><span class="sxs-lookup"><span data-stu-id="38726-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>