---
title: Counter Width-Quantum Development Kit
description: 'Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum do policzania liczby qubits przydzielonej i zapożyczonej przez operacje w Q# programie.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691120"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="fbf00-103">Symulator śledzenia Quantum: szerokość licznika</span><span class="sxs-lookup"><span data-stu-id="fbf00-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="fbf00-104">Licznik width jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="fbf00-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="fbf00-105">Można jej użyć do zliczenia liczby qubits przydzielone i zapożyczone przez poszczególne operacje w Q# programie.</span><span class="sxs-lookup"><span data-stu-id="fbf00-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="fbf00-106">Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits, na przykład pomnóż `X` operacje kontrolowane lub `T` operacje kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="fbf00-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="fbf00-107">Wywoływanie licznika szerokości</span><span class="sxs-lookup"><span data-stu-id="fbf00-107">Invoking the width counter</span></span>

<span data-ttu-id="fbf00-108">Aby uruchomić symulator śledzenia Quantum z licznikiem szerokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseWidthCounter` Właściwość na **true** , a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie przy użyciu `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="fbf00-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="fbf00-109">Używanie licznika Width w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="fbf00-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="fbf00-110">W poniższym przykładzie w języku C# jest obliczana liczba dodatkowych qubits przyznanych przez implementację <xref:Microsoft.Quantum.Intrinsic.X> operacji mnożenia, na podstawie następującego Q# przykładowego kodu:</span><span class="sxs-lookup"><span data-stu-id="fbf00-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="fbf00-111">Operacja mnożenia z mnożeniem <xref:Microsoft.Quantum.Intrinsic.X> działa na ogół pięciu qubits, przydziela dwa [pomocnicze qubits](xref:microsoft.quantum.glossary#ancilla)i ma szerokość wejściową **5** .</span><span class="sxs-lookup"><span data-stu-id="fbf00-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="fbf00-112">Aby sprawdzić liczbę liczników, użyj następującego programu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="fbf00-112">Use the following C# program to verify the counts:</span></span>

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

<span data-ttu-id="fbf00-113">W pierwszej części programu jest uruchamiana `ApplyMultiControlledX` operacja.</span><span class="sxs-lookup"><span data-stu-id="fbf00-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="fbf00-114">Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby przydzielonej qubits oraz liczby qubits, które `Controlled X` operacja otrzymała jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="fbf00-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="fbf00-115">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik szerokość w formacie CSV, korzystając z następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="fbf00-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="fbf00-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fbf00-116">See also</span></span>

- <span data-ttu-id="fbf00-117">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="fbf00-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="fbf00-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="fbf00-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="fbf00-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="fbf00-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="fbf00-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="fbf00-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
