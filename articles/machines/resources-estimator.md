---
title: Szacowania zasobów zestawu Quantum Development Kit | Microsoft Docs
description: Omówienie zasobów zestawu Quantum Development Kit firmy Microsoft szacowania
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 960fda3dade7648f9cd24496c3a49fd11d6f807a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820865"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="3d450-103">Maszyna docelowa ResourcesEstimator</span><span class="sxs-lookup"><span data-stu-id="3d450-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="3d450-104">Jak nazywa się, `ResourcesEstimator` szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="3d450-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="3d450-105">Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu można oszacować zasoby dla operacji Q #, które używają tysięcy qubits.</span><span class="sxs-lookup"><span data-stu-id="3d450-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="3d450-106">Użycie</span><span class="sxs-lookup"><span data-stu-id="3d450-106">Usage</span></span>

<span data-ttu-id="3d450-107">`ResourcesEstimator` jest tylko innym typem maszyny docelowej, dlatego może służyć do uruchamiania dowolnej operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="3d450-108">W przypadku innych maszyn docelowych, aby użyć jej w C# programie hosta, Utwórz wystąpienie i przekaż je jako pierwszy parametr metody `Run` operacji:</span><span class="sxs-lookup"><span data-stu-id="3d450-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="3d450-109">Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia metodę `ToTSV()`, aby wygenerować tabelę z wartościami rozdzielanymi znakami tabulacji (TSV), które można zapisać w pliku lub zapisać w konsoli programu w celu przeprowadzenia analizy.</span><span class="sxs-lookup"><span data-stu-id="3d450-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="3d450-110">Dane wyjściowe powyższego programu powinny wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="3d450-110">The output of the above program should look something like this:</span></span>

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="3d450-111">`ResourcesEstimator` nie resetuje obliczeń dla każdego przebiegu, jeśli to samo wystąpienie jest używane do wykonania kolejnej operacji, spowoduje to zachowywanie liczby agregowania na podstawie istniejących wyników.</span><span class="sxs-lookup"><span data-stu-id="3d450-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="3d450-112">Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego wykonania.</span><span class="sxs-lookup"><span data-stu-id="3d450-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="3d450-113">Programowe pobieranie szacowanych danych</span><span class="sxs-lookup"><span data-stu-id="3d450-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="3d450-114">Oprócz tabeli TSV, szacowane zasoby mogą być pobierane programowo za pośrednictwem właściwości `Data` `ResourcesEstimator`.</span><span class="sxs-lookup"><span data-stu-id="3d450-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="3d450-115">`Data` udostępnia wystąpienie `System.DataTable` z dwiema kolumnami: `Metric` i `Sum`, indeksowane przez nazwy metryk.</span><span class="sxs-lookup"><span data-stu-id="3d450-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="3d450-116">Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford`, `T` i `CNOT` bram używanych przez operację Q #:</span><span class="sxs-lookup"><span data-stu-id="3d450-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="3d450-117">Zgłoszone metryki</span><span class="sxs-lookup"><span data-stu-id="3d450-117">Metrics Reported</span></span>

<span data-ttu-id="3d450-118">Poniżej znajduje się lista metryk szacowanych przez `ResourcesEstimator`:</span><span class="sxs-lookup"><span data-stu-id="3d450-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="3d450-119">__CNOT__: liczba wykonanych bram CNOT (znanych także jako kontrolowane bramy Pauli X).</span><span class="sxs-lookup"><span data-stu-id="3d450-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="3d450-120">__QubitClifford__: liczba wykonanych pojedynczej bramy qubit Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="3d450-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="3d450-121">__Miara__: liczba wykonanych pomiarów.</span><span class="sxs-lookup"><span data-stu-id="3d450-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="3d450-122">__R__: liczba wykonanych pojedynczych rotacji qubit, z wyjątkiem bram T, Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="3d450-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="3d450-123">__T__: liczba bram t i ich sprzężenia, łącznie z bramą t, T_x = H. T. H i T_y = HY. t. HY, wykonane.</span><span class="sxs-lookup"><span data-stu-id="3d450-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="3d450-124">__Głębokość__: Głębokość obwodu Quantum wykonywanego przez operację Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="3d450-125">Domyślnie tylko bramy T są zliczane na głębokości, szczegóły można znaleźć w temacie [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="3d450-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="3d450-126">__Width__: Maksymalna liczba qubits przypisana podczas wykonywania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="3d450-127">__BorrowedWidth__: Maksymalna liczba qubits została zapożyczone w ramach operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="3d450-128">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="3d450-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="3d450-129"><xref:microsoft.quantum.intrinsic.assertprob> z przestrzeni nazw <xref:microsoft.quantum.intrinsic> można użyć, aby podać informacje o oczekiwanym prawdopodobieństwie pomiaru, aby ułatwić wykonanie programu Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="3d450-130">Zostało to przedstawione w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d450-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="3d450-131">Gdy `ResourcesEstimator` napotka `AssertProb`, nastąpi zapisanie `PauliZ` pomiaru na `source` i `q` należy otrzymać wynik `Zero` z prawdopodobieństwem 0,5.</span><span class="sxs-lookup"><span data-stu-id="3d450-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="3d450-132">Gdy zostanie on wykonany `M` później, będzie znajdował zarejestrowane wartości prawdopodobieństwa wyniku i `M` zwróci `Zero` lub `One` z prawdopodobieństwem 0,5.</span><span class="sxs-lookup"><span data-stu-id="3d450-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="3d450-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3d450-133">See also</span></span>

<span data-ttu-id="3d450-134">`ResourcesEstimator` jest tworzona na podstawie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum, który zapewnia bogatszy zestaw metryk, możliwość raportowania metryk w pełnym wywołaniu grafu i funkcji, takich jak [odrębne dane wejściowe](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , aby ułatwić znajdowanie usterek w programach Q #.</span><span class="sxs-lookup"><span data-stu-id="3d450-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="3d450-135">Aby uzyskać więcej informacji, zapoznaj się z dokumentacją dotyczącą [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="3d450-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

