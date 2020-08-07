---
title: Przykładowe aplikacje dla biblioteki Quantum Chemistry
description: Przyjrzyj się przykładowym aplikacjom dla biblioteki Microsoft Quantum Chemistry.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869294"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="4241b-103">Przykłady dla chemii kwantowej</span><span class="sxs-lookup"><span data-stu-id="4241b-103">Quantum chemistry examples</span></span>

<span data-ttu-id="4241b-104">W pojęciach dotyczących chemii kwantowej ręcznie konstruowaliśmy przykładowe hamiltoniany fermionów.</span><span class="sxs-lookup"><span data-stu-id="4241b-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="4241b-105">Teraz w bibliotece canon łączymy algorytmy symulacji chemicznej opisane w artykule [Symulowanie dynamiki Hamiltona](xref:microsoft.quantum.libraries.standard.algorithms) z [szacowaniem fazy kwantowej](xref:microsoft.quantum.libraries.characterization).</span><span class="sxs-lookup"><span data-stu-id="4241b-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="4241b-106">Ta kombinacja pozwala nam uzyskać szacunkowe poziomy energii w reprezentowanej molekule. Jest to jedno z kluczowych zastosowań chemii kwantowej na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="4241b-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="4241b-107">Zamiast pojedynczo określać warunki hamiltonianów, analizujemy również niektóre przykłady, dzięki czemu możemy wykonywać eksperymenty z zakresu chemii kwantowej na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="4241b-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="4241b-108">Zaczynamy od przykładów, które ładują hamiltonian z dziedziny chemii zakodowany w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="4241b-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="4241b-109">W przypadku molekuł, które są zbyt duże, aby je symulować na [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), można nadal uprawiać interesującą naukę.</span><span class="sxs-lookup"><span data-stu-id="4241b-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="4241b-110">Na przykład koszty zasobów związane z wykonywaniem dużych symulacji chemicznych mogą być nadal oceniane przy użyciu [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="4241b-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="4241b-111">Spróbujmy teraz zilustrować interesujące zastosowania biblioteki symulacji chemicznych za pomocą kilku z udostępnionych przykładów.</span><span class="sxs-lookup"><span data-stu-id="4241b-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
