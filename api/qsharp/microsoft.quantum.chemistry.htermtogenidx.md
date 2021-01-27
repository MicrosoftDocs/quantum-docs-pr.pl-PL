---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839613"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="04bfa-102">HTermToGenIdx, funkcja</span><span class="sxs-lookup"><span data-stu-id="04bfa-102">HTermToGenIdx function</span></span>

<span data-ttu-id="04bfa-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="04bfa-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="04bfa-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="04bfa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="04bfa-105">Konwertuje termin hamiltonian w `HTerm` formacie danych na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="04bfa-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="04bfa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04bfa-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="04bfa-107">termin: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="04bfa-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="04bfa-108">Dane wejściowe w `HTerm` formacie.</span><span class="sxs-lookup"><span data-stu-id="04bfa-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="04bfa-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04bfa-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="04bfa-110">Dodatkowe informacje dodane do GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="04bfa-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="04bfa-111">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="04bfa-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="04bfa-112">GeneratorIndex reprezentujący termin hamiltonian reprezentowany przez `term` , wraz z dodatkowymi informacjami dodanymi przez `termType` .</span><span class="sxs-lookup"><span data-stu-id="04bfa-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>