---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713986"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="aefa0-102">JordanWignerGeneratorSystem, funkcja</span><span class="sxs-lookup"><span data-stu-id="aefa0-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="aefa0-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="aefa0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="aefa0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aefa0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aefa0-105">Konwertuje hamiltonian opisane przez `JWOptimizedHTerms` do, `GeneratorSystem` wyrażone w zakresie `GeneratorIndex` Konwencji zdefiniowanej w tym pliku.</span><span class="sxs-lookup"><span data-stu-id="aefa0-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="aefa0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aefa0-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="aefa0-107">dane: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="aefa0-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="aefa0-108">Opis elementu hamiltonian w `JWOptimizedHTerms` formacie.</span><span class="sxs-lookup"><span data-stu-id="aefa0-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="aefa0-109">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="aefa0-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="aefa0-110">Reprezentacja hamiltonian jako `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="aefa0-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>