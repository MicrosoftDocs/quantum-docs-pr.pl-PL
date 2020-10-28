---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: c75dcd655dafb7048f61f4b07b852cc5f437275d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714056"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a><span data-ttu-id="7adad-102">JordanWignerClusterOperatorGeneratorSystem, funkcja</span><span class="sxs-lookup"><span data-stu-id="7adad-102">JordanWignerClusterOperatorGeneratorSystem function</span></span>

<span data-ttu-id="7adad-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7adad-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7adad-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7adad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7adad-105">Konwertuje hamiltonian opisane przez `JWOptimizedHTerms` do, `GeneratorSystem` wyrażone w zakresie `GeneratorIndex` Konwencji zdefiniowanej w tym pliku.</span><span class="sxs-lookup"><span data-stu-id="7adad-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="7adad-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7adad-106">Input</span></span>

### <a name="data--jordanwignerinputstate"></a><span data-ttu-id="7adad-107">dane: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="7adad-107">data : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="7adad-108">Opis elementu hamiltonian w `JWOptimizedHTerms` formacie.</span><span class="sxs-lookup"><span data-stu-id="7adad-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="7adad-109">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="7adad-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="7adad-110">Reprezentacja hamiltonian jako `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="7adad-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>