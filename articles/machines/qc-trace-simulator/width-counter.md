---
title: Licznik szerokości
description: Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który zlicza qubits przydzielone i pożyczone przez poszczególne operacje w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907090"
---
# <a name="width-counter"></a><span data-ttu-id="a5ddd-103">Licznik szerokości</span><span class="sxs-lookup"><span data-stu-id="a5ddd-103">Width Counter</span></span>

<span data-ttu-id="a5ddd-104">`Width Counter` liczy liczbę qubits przydzielone i pożyczone przez każdą operację.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="a5ddd-105">Wszystkie operacje z przestrzeni nazw `Microsoft.Quantum.Intrinsic` są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="a5ddd-106">Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="a5ddd-107">Na przykład pomnóż kontrolowane bramy `X` lub kontrolowane `T` bramy.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="a5ddd-108">Poinformuj nas o liczbie dodatkowych qubits przyznanych przez implementację pomnożenia `X` bramę:</span><span class="sxs-lookup"><span data-stu-id="a5ddd-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="a5ddd-109">Używanie licznika szerokości w ramach C# programu</span><span class="sxs-lookup"><span data-stu-id="a5ddd-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="a5ddd-110">Mnożenie kontrolowane `X` działające na ogół 5 qubits przydzieli 2 dodatkowe qubits, a Szerokość wejściowa będzie wynosić 5.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="a5ddd-111">Aby sprawdzić, czy tak jest, można użyć następującego C# programu:</span><span class="sxs-lookup"><span data-stu-id="a5ddd-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

<span data-ttu-id="a5ddd-112">Pierwsza część programu jest wykonywana `ApplyMultiControlledX`.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="a5ddd-113">W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać liczbę przydzieloną qubits oraz liczbę qubits, które są `X` kontrolowane jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="a5ddd-114">Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik szerokości w formacie CSV można użyć następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="a5ddd-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="a5ddd-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5ddd-115">See also</span></span> ##

- <span data-ttu-id="a5ddd-116">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="a5ddd-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
