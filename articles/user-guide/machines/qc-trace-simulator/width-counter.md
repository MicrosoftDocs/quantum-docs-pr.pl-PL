---
title: Counter Width-Quantum Development Kit
description: 'Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum, aby policzyć liczbę qubits przydzieloną i zaciągniętych przez operacje w programie Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871524"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="be427-103">Symulator śledzenia Quantum: szerokość licznika</span><span class="sxs-lookup"><span data-stu-id="be427-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="be427-104">Licznik width jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="be427-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="be427-105">Można jej użyć do zliczenia liczby qubits przydzielone i zapożyczone przez każdą operację w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="be427-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="be427-106">Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits, na przykład pomnóż `X` operacje kontrolowane lub `T` operacje kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="be427-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="be427-107">Wywoływanie licznika szerokości</span><span class="sxs-lookup"><span data-stu-id="be427-107">Invoking the width counter</span></span>

<span data-ttu-id="be427-108">Aby uruchomić symulator śledzenia Quantum z licznikiem szerokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseWidthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie przy użyciu `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="be427-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="be427-109">Używanie licznika Width w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="be427-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="be427-110">W poniższym przykładzie w języku C# jest obliczana liczba dodatkowych qubits przyznanych przez implementację <xref:microsoft.quantum.intrinsic.x> operacji mnożenia, na podstawie następującego przykładowego kodu Q #:</span><span class="sxs-lookup"><span data-stu-id="be427-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="be427-111">Operacja mnożenia z mnożeniem <xref:microsoft.quantum.intrinsic.x> działa na ogół pięciu qubits, przydziela dwa [pomocnicze qubits](xref:microsoft.quantum.glossary#ancilla)i ma szerokość wejściową **5**.</span><span class="sxs-lookup"><span data-stu-id="be427-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="be427-112">Aby sprawdzić liczbę liczników, użyj następującego programu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="be427-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="be427-113">W pierwszej części programu jest uruchamiana `ApplyMultiControlledX` operacja.</span><span class="sxs-lookup"><span data-stu-id="be427-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="be427-114">Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby przydzielonej qubits oraz liczby qubits, które `Controlled X` operacja otrzymała jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="be427-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="be427-115">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik szerokość w formacie CSV, korzystając z następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="be427-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="be427-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="be427-116">See also</span></span>

- <span data-ttu-id="be427-117">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="be427-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="be427-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="be427-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="be427-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="be427-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="be427-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="be427-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
