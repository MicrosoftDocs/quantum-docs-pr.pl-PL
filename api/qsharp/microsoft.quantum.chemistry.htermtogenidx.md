---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714835"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="4d3ef-102">HTermToGenIdx, funkcja</span><span class="sxs-lookup"><span data-stu-id="4d3ef-102">HTermToGenIdx function</span></span>

<span data-ttu-id="4d3ef-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4d3ef-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="4d3ef-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d3ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d3ef-105">Konwertuje termin hamiltonian w `HTerm` formacie danych na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="4d3ef-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="4d3ef-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4d3ef-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="4d3ef-107">termin: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="4d3ef-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="4d3ef-108">Dane wejściowe w `HTerm` formacie.</span><span class="sxs-lookup"><span data-stu-id="4d3ef-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="4d3ef-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4d3ef-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4d3ef-110">Dodatkowe informacje dodane do GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="4d3ef-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="4d3ef-111">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4d3ef-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4d3ef-112">GeneratorIndex reprezentujący termin hamiltonian reprezentowany przez `term` , wraz z dodatkowymi informacjami dodanymi przez `termType` .</span><span class="sxs-lookup"><span data-stu-id="4d3ef-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>