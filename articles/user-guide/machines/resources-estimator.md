---
title: Zasoby Quantum szacowania-Quantum Development Kit
description: Dowiedz się więcej o programie Microsoft QDKe szacowania, który szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze z systemem Quantum.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835931"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="4ec4a-103">Zasoby zestawu Quantum Development Kit (QDK) szacowania</span><span class="sxs-lookup"><span data-stu-id="4ec4a-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="4ec4a-104">Jak nazwa oznacza, `ResourcesEstimator` Klasa szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="4ec4a-105">Jest to wykonywane przez uruchomienie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu szacuje zasoby dla Q# operacji, które korzystają z tysięcy qubits, pod warunkiem, że klasyczna część kodu jest uruchamiana w rozsądnym czasie.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="4ec4a-106">Szacowania zasobów jest oparty na [symulatorze śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), który zapewnia bogatszy zestaw metryk i narzędzi ułatwiających debugowanie Q# programów.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="4ec4a-107">Wywoływanie i uruchamianie zasobów szacowania</span><span class="sxs-lookup"><span data-stu-id="4ec4a-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="4ec4a-108">Możesz użyć szacowania zasobów do uruchomienia dowolnej Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="4ec4a-109">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="4ec4a-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="4ec4a-110">Wywoływanie zasobów szacowania z języka C #</span><span class="sxs-lookup"><span data-stu-id="4ec4a-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="4ec4a-111">Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `ResourceEstimator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="4ec4a-112">Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `ResourceEstimator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="4ec4a-113">Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę, która generuje tabelę z wartościami rozdzielonymi tabulatorami (tsv).</span><span class="sxs-lookup"><span data-stu-id="4ec4a-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="4ec4a-114">Tabelę można zapisać w pliku lub wyświetlić w konsoli programu na potrzeby analizy.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="4ec4a-115">Poniżej przedstawiono przykładowe dane wyjściowe z poprzedniego programu:</span><span class="sxs-lookup"><span data-stu-id="4ec4a-115">The following is a sample output from the preceding program:</span></span>

```output
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
> <span data-ttu-id="4ec4a-116">`ResourcesEstimator`Wystąpienie nie resetuje obliczeń dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="4ec4a-117">Jeśli używasz tego samego wystąpienia do uruchomienia innej operacji, agreguje nowe wyniki z istniejącymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="4ec4a-118">Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="4ec4a-119">Wywoływanie zasobów szacowania z języka Python</span><span class="sxs-lookup"><span data-stu-id="4ec4a-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="4ec4a-120">Użyj metody [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną Q# operacją:</span><span class="sxs-lookup"><span data-stu-id="4ec4a-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="4ec4a-121">Wywoływanie zasobów szacowania z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="4ec4a-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="4ec4a-122">Podczas uruchamiania Q# programu z wiersza polecenia należy użyć parametru **--symulatora** (lub **-s** ), aby określić `ResourcesEstimator` maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="4ec4a-123">Następujące polecenie uruchamia program przy użyciu szacowania zasobów:</span><span class="sxs-lookup"><span data-stu-id="4ec4a-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="4ec4a-124">Wywoływanie zasobów szacowania z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="4ec4a-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="4ec4a-125">Q#Aby uruchomić operację, użyj polecenia I [oszacowania% oszacowanie](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .</span><span class="sxs-lookup"><span data-stu-id="4ec4a-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="4ec4a-126">Programowe pobieranie szacowanych danych</span><span class="sxs-lookup"><span data-stu-id="4ec4a-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="4ec4a-127">Oprócz tabeli TSV można programowo pobrać zasoby szacowane podczas wykonywania przez `Data` Właściwość zasobów szacowania.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="4ec4a-128">`Data`Właściwość zawiera `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="4ec4a-129">Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` operacji oraz operacje wykonywane przez Q# operację:</span><span class="sxs-lookup"><span data-stu-id="4ec4a-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="4ec4a-130">Zgłoszone metryki</span><span class="sxs-lookup"><span data-stu-id="4ec4a-130">Metrics Reported</span></span>

<span data-ttu-id="4ec4a-131">Szacowania zasobów śledzi następujące metryki:</span><span class="sxs-lookup"><span data-stu-id="4ec4a-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="4ec4a-132">Metryka</span><span class="sxs-lookup"><span data-stu-id="4ec4a-132">Metric</span></span>|<span data-ttu-id="4ec4a-133">Opis</span><span class="sxs-lookup"><span data-stu-id="4ec4a-133">Description</span></span>|
|----|----|
|<span data-ttu-id="4ec4a-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-134">__CNOT__</span></span>    |<span data-ttu-id="4ec4a-135">Liczba uruchomień `CNOT` operacji (znanych także jako kontrolowane operacje Pauli X).</span><span class="sxs-lookup"><span data-stu-id="4ec4a-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="4ec4a-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-136">__QubitClifford__</span></span> |<span data-ttu-id="4ec4a-137">Liczba uruchomień pojedynczego qubit Clifford i Pauli operacji.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="4ec4a-138">__miara__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-138">__Measure__</span></span>    |<span data-ttu-id="4ec4a-139">Liczba uruchomień pomiarów.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="4ec4a-140">__R__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-140">__R__</span></span>    |<span data-ttu-id="4ec4a-141">Liczba uruchomień wszystkich rotacji qubit, z wyjątkiem `T` operacji Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="4ec4a-142">__T__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-142">__T__</span></span>    |<span data-ttu-id="4ec4a-143">Liczba uruchomień `T` operacji i ich sprzężenia, w tym `T` operacje, T_x = H. T. H i T_y = HY. T. HY.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="4ec4a-144">__Ścisł__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-144">__Depth__</span></span>|<span data-ttu-id="4ec4a-145">Dolna granica głębokości obwodu Quantum uruchamianego przez Q# operację.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="4ec4a-146">Domyślnie Metryka głębokości liczy tylko `T` bramy.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="4ec4a-147">Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="4ec4a-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="4ec4a-148">__Szerokość__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-148">__Width__</span></span>    |<span data-ttu-id="4ec4a-149">Dolna granica maksymalnej liczby qubits przydzieloną podczas uruchamiania Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="4ec4a-150">Jednocześnie może nie być możliwe równoczesne osiąganie __głębokości__ i dolnej granicy __szerokości__ .</span><span class="sxs-lookup"><span data-stu-id="4ec4a-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="4ec4a-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="4ec4a-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="4ec4a-152">Maksymalna liczba qubits zaciągniętych w ramach Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="4ec4a-153">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="4ec4a-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="4ec4a-154">Możesz użyć <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> przestrzeni nazw, aby podać informacje o oczekiwanym prawdopodobieństwie operacji pomiaru.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="4ec4a-155">Aby uzyskać więcej informacji, zobacz [symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="4ec4a-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="4ec4a-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4ec4a-156">See also</span></span>

- [<span data-ttu-id="4ec4a-157">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="4ec4a-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="4ec4a-158">Kwantowy symulator Toffoli</span><span class="sxs-lookup"><span data-stu-id="4ec4a-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="4ec4a-159">Kwantowy symulator pełnego stanu</span><span class="sxs-lookup"><span data-stu-id="4ec4a-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 