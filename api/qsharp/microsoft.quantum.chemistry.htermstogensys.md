---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204117"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="06ac9-102">HTermsToGenSys, funkcja</span><span class="sxs-lookup"><span data-stu-id="06ac9-102">HTermsToGenSys function</span></span>

<span data-ttu-id="06ac9-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="06ac9-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="06ac9-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="06ac9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="06ac9-105">Konwertuje hamiltonian w `HTerm[]` formacie danych na GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="06ac9-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="06ac9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="06ac9-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="06ac9-107">dane: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="06ac9-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="06ac9-108">Dane wejściowe w `HTerm[]` formacie.</span><span class="sxs-lookup"><span data-stu-id="06ac9-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="06ac9-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="06ac9-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="06ac9-110">Dodatkowe informacje dodane do GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="06ac9-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="06ac9-111">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="06ac9-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="06ac9-112">GeneratorSystem reprezentujący hamiltonian reprezentowane przez dane wejściowe `data` .</span><span class="sxs-lookup"><span data-stu-id="06ac9-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>