---
title: Szacowania zasobów zestawu Quantum Development Kit
description: 'Dowiedz się więcej o zasobach szacowania, które szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415265"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="7f933-103">Maszyna docelowa szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="7f933-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="7f933-104">Jako że nazwa oznacza, `ResourcesEstimator` szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="7f933-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="7f933-105">Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu można oszacować zasoby dla operacji Q #, które używają tysięcy qubits, jeśli klasyczna część kodu może być uruchamiana w rozsądnym czasie.</span><span class="sxs-lookup"><span data-stu-id="7f933-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="7f933-106">Użycie</span><span class="sxs-lookup"><span data-stu-id="7f933-106">Usage</span></span>

<span data-ttu-id="7f933-107">`ResourcesEstimator`Jest to tylko inny typ maszyny docelowej, dlatego może służyć do uruchamiania dowolnej operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="7f933-108">Innymi maszynami docelowymi, aby użyć ich w programie hosta C# i utworzyć wystąpienie i przekazać je jako pierwszy parametr `Run` metody operacji:</span><span class="sxs-lookup"><span data-stu-id="7f933-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="7f933-109">Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę generowania tabeli z wartościami rozdzielanymi znakami tabulacji (tsv), które można zapisać w pliku lub zapisaniem w konsoli programu na potrzeby analizy.</span><span class="sxs-lookup"><span data-stu-id="7f933-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="7f933-110">Dane wyjściowe powyższego programu powinny wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="7f933-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="7f933-111">Nie `ResourcesEstimator` resetuje obliczeń dla każdego przebiegu, jeśli to samo wystąpienie jest używane do wykonania kolejnej operacji, spowoduje to zachowanie agregowania liczników na podstawie istniejących wyników.</span><span class="sxs-lookup"><span data-stu-id="7f933-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="7f933-112">Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego wykonania.</span><span class="sxs-lookup"><span data-stu-id="7f933-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="7f933-113">Programowe pobieranie szacowanych danych</span><span class="sxs-lookup"><span data-stu-id="7f933-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="7f933-114">Oprócz tabeli TSV, szacowane zasoby mogą być pobierane programowo za pośrednictwem `ResourcesEstimator` `Data` właściwości.</span><span class="sxs-lookup"><span data-stu-id="7f933-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="7f933-115">`Data`oferuje `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.</span><span class="sxs-lookup"><span data-stu-id="7f933-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="7f933-116">Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` bram używanych przez operację Q #:</span><span class="sxs-lookup"><span data-stu-id="7f933-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="7f933-117">Zgłoszone metryki</span><span class="sxs-lookup"><span data-stu-id="7f933-117">Metrics Reported</span></span>

<span data-ttu-id="7f933-118">Poniżej znajduje się lista metryk szacowanych przez `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="7f933-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="7f933-119">__CNOT__: liczba wykonanych bram CNOT (znanych także jako kontrolowane bramy Pauli X).</span><span class="sxs-lookup"><span data-stu-id="7f933-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="7f933-120">__QubitClifford__: liczba wykonanych pojedynczej bramy qubit Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="7f933-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="7f933-121">__Miara__: liczba wykonanych pomiarów.</span><span class="sxs-lookup"><span data-stu-id="7f933-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="7f933-122">__R__: liczba wykonanych pojedynczych rotacji qubit, z wyjątkiem bram T, Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="7f933-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="7f933-123">__T__: liczba bram t i ich sprzężenia, łącznie z bramą t, T_x = H. T. H i T_y = HY. t. HY, wykonane.</span><span class="sxs-lookup"><span data-stu-id="7f933-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="7f933-124">__Głębokość__: Dolna granica głębokości obwodu Quantum wykonywanego przez operację Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-124">__Depth__: The lower bound for the depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="7f933-125">Domyślnie tylko bramy T są zliczane na głębokości, szczegóły można znaleźć w temacie [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="7f933-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="7f933-126">__Width__: Dolna granica dla maksymalnej liczby qubits przydzieloną podczas wykonywania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-126">__Width__: The lower bound for the maximum number of qubits allocated during the execution of the Q# operation.</span></span> <span data-ttu-id="7f933-127">Jednocześnie może nie być możliwe równoczesne osiąganie __głębokości__ i dolnej granicy __szerokości__ .</span><span class="sxs-lookup"><span data-stu-id="7f933-127">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>
* <span data-ttu-id="7f933-128">__BorrowedWidth__: Maksymalna liczba qubits została zapożyczone w ramach operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-128">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="7f933-129">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="7f933-129">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="7f933-130"><xref:microsoft.quantum.intrinsic.assertprob>z <xref:microsoft.quantum.intrinsic> przestrzeni nazw można korzystać w celu podania informacji o oczekiwanym prawdopodobieństwie pomiaru, aby ułatwić wykonanie programu Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-130"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="7f933-131">Zostało to przedstawione w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="7f933-131">The following example illustrates this:</span></span>

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

<span data-ttu-id="7f933-132">Gdy `ResourcesEstimator` napotkają, `AssertProb` nastąpi zapisanie tego, że pomiar jest `PauliZ` włączony `source` i `q` powinien zostać uzyskany wynik `Zero` prawdopodobieństwa 0,5.</span><span class="sxs-lookup"><span data-stu-id="7f933-132">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="7f933-133">Gdy zostanie on wykonany `M` później, znajdzie zarejestrowane wartości prawdopodobieństwa wyniku i `M` zwróci `Zero` lub `One` z prawdopodobieństwem 0,5.</span><span class="sxs-lookup"><span data-stu-id="7f933-133">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="7f933-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7f933-134">See also</span></span>

<span data-ttu-id="7f933-135">`ResourcesEstimator`Jest zbudowany na podstawie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum, który zapewnia bogatszy zestaw metryk, możliwość zgłaszania metryk w całym grafie wywołań i funkcji, takich jak [różne dane wejściowe](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , aby pomóc w znalezieniu usterek w programach Q #.</span><span class="sxs-lookup"><span data-stu-id="7f933-135">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="7f933-136">Aby uzyskać więcej informacji, zapoznaj się z dokumentacją dotyczącą [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="7f933-136">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

