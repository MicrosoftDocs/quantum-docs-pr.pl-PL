---
title: Symulatory kwantowe i programy w języku Q#
description: Opisuje symulatory kwantowe dostępne jako maszyny docelowe dla programów w języku Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868308"
---
# <a name="quantum-simulators"></a><span data-ttu-id="a2df3-103">Symulatory kwantowe</span><span class="sxs-lookup"><span data-stu-id="a2df3-103">Quantum simulators</span></span>

<span data-ttu-id="a2df3-104">Symulatory kwantowe to programy działające na klasycznych komputerach pełniące rolę *maszyny docelowej* dla programu w języku Q# i umożliwiające uruchamianie oraz testowanie programów kwantowych w środowisku, które przewiduje, jak kubity będą reagować na różne operacje.</span><span class="sxs-lookup"><span data-stu-id="a2df3-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="a2df3-105">W tym artykule opisano, które symulatory kwantowe są dołączone do zestawu Quantum Development Kit (QDK), a także różne sposoby przekazywania programu w języku Q# do symulatorów kwantowych, na przykład za pośrednictwem wiersza polecenia lub przy użyciu kodu sterownika napisanego w języku klasycznym.</span><span class="sxs-lookup"><span data-stu-id="a2df3-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="a2df3-106">Symulatory kwantowe zestawu Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a2df3-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="a2df3-107">Symulator kwantowy zapewnia implementacje kwantowych typów pierwotnych algorytmu.</span><span class="sxs-lookup"><span data-stu-id="a2df3-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="a2df3-108">Obejmują one operacje pierwotne, takie jak `H`, `CNOT` i `Measure`, a także śledzenie kubitów i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="a2df3-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="a2df3-109">Zestaw QDK zawiera różne klasy symulatorów kwantowych reprezentujące różne modele wykonywania dla tego samego algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="a2df3-109">The QDK includes different classes of quantum simulators representing different execution models for the same quantum algorithm.</span></span> 


<span data-ttu-id="a2df3-110">Każdy typ symulatora kwantowego może udostępniać odrębną implementację typów pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="a2df3-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="a2df3-111">Na przykład [symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator) uruchamia algorytm kwantowy, w pełni symulując [wektor stanu kwantowego](xref:microsoft.quantum.glossary#quantum-state), podczas gdy [symulator śledzenia komputera kwantowego](xref:microsoft.quantum.machines.qc-trace-simulator.intro) w ogóle nie uwzględnia rzeczywistego stanu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="a2df3-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="a2df3-112">Zamiast tego śledzi on użycie bramy, kubitów oraz innych zasobów.</span><span class="sxs-lookup"><span data-stu-id="a2df3-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="a2df3-113">Klasy maszyn kwantowych</span><span class="sxs-lookup"><span data-stu-id="a2df3-113">Quantum machine classes</span></span>

<span data-ttu-id="a2df3-114">W przyszłości w zestawie QDK zostaną zdefiniowane dodatkowe klasy maszyn kwantowych umożliwiające obsługę innych typów symulacji oraz wykonywanie na sprzęcie kwantowym.</span><span class="sxs-lookup"><span data-stu-id="a2df3-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support execution on quantum hardware.</span></span> <span data-ttu-id="a2df3-115">Zapewnienie niezmienności algorytmu przy różnych bazowych implementacjach na maszynach ułatwia jego testowanie i debugowanie w symulacji, a następnie uruchamianie na używanym komputerze z poczuciem pewności, że nie został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="a2df3-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="a2df3-116">Zestaw QDK zawiera kilka klas maszyn kwantowych, z których wszystkie są zdefiniowane w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="a2df3-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="a2df3-117">Symulator</span><span class="sxs-lookup"><span data-stu-id="a2df3-117">Simulator</span></span> |<span data-ttu-id="a2df3-118">Klasa</span><span class="sxs-lookup"><span data-stu-id="a2df3-118">Class</span></span>|<span data-ttu-id="a2df3-119">Opis</span><span class="sxs-lookup"><span data-stu-id="a2df3-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="a2df3-120">Symulator pełnego stanu</span><span class="sxs-lookup"><span data-stu-id="a2df3-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="a2df3-121">Uruchamia oraz debuguje algorytmy kwantowe i jest ograniczony do około 30 kubitów.</span><span class="sxs-lookup"><span data-stu-id="a2df3-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="a2df3-122">Proste narzędzie do szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="a2df3-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="a2df3-123">Wykonuje ogólną analizę zasobów wymaganych do uruchomienia algorytmu kwantowego i obsługuje tysiące kubitów.</span><span class="sxs-lookup"><span data-stu-id="a2df3-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="a2df3-124">Oparte na śledzeniu narzędzie do szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="a2df3-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="a2df3-125">Uruchamia zaawansowaną analizę zużycia zasobów dla całego grafu wywołań algorytmu i obsługuje tysiące kubitów.</span><span class="sxs-lookup"><span data-stu-id="a2df3-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="a2df3-126">Symulator Toffoli</span><span class="sxs-lookup"><span data-stu-id="a2df3-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="a2df3-127">Symuluje algorytmy kwantowe ograniczone do operacji `X` i `CNOT` oraz kontrolowanych wielokrotnie operacji kwantowych `X`; obsługuje tysiące kubitów.</span><span class="sxs-lookup"><span data-stu-id="a2df3-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="a2df3-128">Wywoływanie symulatora kwantowego</span><span class="sxs-lookup"><span data-stu-id="a2df3-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="a2df3-129">W sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs) przedstawiono trzy sposoby przekazywania kodu w języku Q# do symulatora kwantowego:</span><span class="sxs-lookup"><span data-stu-id="a2df3-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="a2df3-130">Za pomocą wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="a2df3-130">Using the command line</span></span>
* <span data-ttu-id="a2df3-131">Za pomocą programu hosta w języku Python</span><span class="sxs-lookup"><span data-stu-id="a2df3-131">Using a Python host program</span></span>
* <span data-ttu-id="a2df3-132">Za pomocą programu hosta w języku C#</span><span class="sxs-lookup"><span data-stu-id="a2df3-132">Using a C# host program</span></span>

<span data-ttu-id="a2df3-133">Maszyny kwantowe to normalne wystąpienia klas .NET, dlatego tworzy się je przez wywołanie konstruktora, tak jak w przypadku dowolnej klasy .NET.</span><span class="sxs-lookup"><span data-stu-id="a2df3-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="a2df3-134">To, jak zostanie to zrobione, zależy sposobu uruchamiania programu w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="a2df3-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2df3-135">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a2df3-135">Next steps</span></span>

* <span data-ttu-id="a2df3-136">Aby uzyskać szczegółowe informacje o sposobie wywoływania maszyn docelowych dla programów w języku Q# w różnych środowiskach, zobacz [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="a2df3-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
