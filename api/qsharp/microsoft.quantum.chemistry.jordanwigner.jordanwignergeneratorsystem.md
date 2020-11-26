---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 0f6719cfac1c50cd55da30e57b0b5c5214813f24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214725"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="5f2fe-102">JordanWignerGeneratorSystem, funkcja</span><span class="sxs-lookup"><span data-stu-id="5f2fe-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="5f2fe-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5f2fe-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5f2fe-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5f2fe-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5f2fe-105">Konwertuje hamiltonian opisane przez `JWOptimizedHTerms` do, `GeneratorSystem` wyrażone w zakresie `GeneratorIndex` Konwencji zdefiniowanej w tym pliku.</span><span class="sxs-lookup"><span data-stu-id="5f2fe-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="5f2fe-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5f2fe-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="5f2fe-107">dane: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="5f2fe-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="5f2fe-108">Opis elementu hamiltonian w `JWOptimizedHTerms` formacie.</span><span class="sxs-lookup"><span data-stu-id="5f2fe-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="5f2fe-109">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="5f2fe-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="5f2fe-110">Reprezentacja hamiltonian jako `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="5f2fe-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>