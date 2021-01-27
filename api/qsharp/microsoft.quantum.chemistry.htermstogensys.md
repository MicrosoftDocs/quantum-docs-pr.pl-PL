---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851762"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="93039-102">HTermsToGenSys, funkcja</span><span class="sxs-lookup"><span data-stu-id="93039-102">HTermsToGenSys function</span></span>

<span data-ttu-id="93039-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="93039-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="93039-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="93039-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="93039-105">Konwertuje hamiltonian w `HTerm[]` formacie danych na GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="93039-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="93039-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="93039-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="93039-107">dane: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="93039-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="93039-108">Dane wejściowe w `HTerm[]` formacie.</span><span class="sxs-lookup"><span data-stu-id="93039-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="93039-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93039-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93039-110">Dodatkowe informacje dodane do GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="93039-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="93039-111">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="93039-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="93039-112">GeneratorSystem reprezentujący hamiltonian reprezentowane przez dane wejściowe `data` .</span><span class="sxs-lookup"><span data-stu-id="93039-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>