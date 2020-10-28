---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714840"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="fd352-102">HTermsToGenSys, funkcja</span><span class="sxs-lookup"><span data-stu-id="fd352-102">HTermsToGenSys function</span></span>

<span data-ttu-id="fd352-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fd352-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="fd352-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd352-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd352-105">Konwertuje hamiltonian w `HTerm[]` formacie danych na GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="fd352-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="fd352-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fd352-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="fd352-107">dane: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="fd352-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="fd352-108">Dane wejściowe w `HTerm[]` formacie.</span><span class="sxs-lookup"><span data-stu-id="fd352-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="fd352-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fd352-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fd352-110">Dodatkowe informacje dodane do GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="fd352-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="fd352-111">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="fd352-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="fd352-112">GeneratorSystem reprezentujący hamiltonian reprezentowane przez dane wejściowe `data` .</span><span class="sxs-lookup"><span data-stu-id="fd352-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>