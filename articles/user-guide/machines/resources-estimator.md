---
title: Zasoby Quantum szacowania-Quantum Development Kit
description: 'Dowiedz się więcej o programie Microsoft QDKe szacowania, który szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870548"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="87c55-103">Zasoby zestawu Quantum Development Kit (QDK) szacowania</span><span class="sxs-lookup"><span data-stu-id="87c55-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="87c55-104">Jak nazywa się, `ResourcesEstimator` Klasa szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="87c55-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="87c55-105">Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu szacuje zasoby dla operacji Q #, które używają tysięcy qubits, pod warunkiem, że klasyczna część kodu jest uruchamiana w rozsądnym czasie.</span><span class="sxs-lookup"><span data-stu-id="87c55-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="87c55-106">Szacowania zasobów jest oparty na [symulatorze śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), który zapewnia bogatszy zestaw metryk i narzędzi ułatwiających debugowanie programów Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="87c55-107">Wywoływanie i uruchamianie zasobów szacowania</span><span class="sxs-lookup"><span data-stu-id="87c55-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="87c55-108">Możesz użyć szacowania zasobów do uruchomienia dowolnej operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="87c55-109">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania programu Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="87c55-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="87c55-110">Wywoływanie zasobów szacowania z języka C #</span><span class="sxs-lookup"><span data-stu-id="87c55-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="87c55-111">Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie `ResourceEstimator` klasy, a następnie przekazać je jako pierwszy parametr `Run` metody operacji.</span><span class="sxs-lookup"><span data-stu-id="87c55-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="87c55-112">Należy pamiętać, że w przeciwieństwie do `QuantumSimulator` klasy `ResourceEstimator` Klasa nie implementuje <xref:System.IDisposable> interfejsu, dlatego nie trzeba go umieszczać w `using` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="87c55-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="87c55-113">Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę, która generuje tabelę z wartościami rozdzielonymi tabulatorami (tsv).</span><span class="sxs-lookup"><span data-stu-id="87c55-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="87c55-114">Tabelę można zapisać w pliku lub wyświetlić w konsoli programu na potrzeby analizy.</span><span class="sxs-lookup"><span data-stu-id="87c55-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="87c55-115">Poniżej przedstawiono przykładowe dane wyjściowe z poprzedniego programu:</span><span class="sxs-lookup"><span data-stu-id="87c55-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="87c55-116">`ResourcesEstimator`Wystąpienie nie resetuje obliczeń dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="87c55-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="87c55-117">Jeśli używasz tego samego wystąpienia do uruchomienia innej operacji, agreguje nowe wyniki z istniejącymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="87c55-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="87c55-118">Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="87c55-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="87c55-119">Wywoływanie zasobów szacowania z języka Python</span><span class="sxs-lookup"><span data-stu-id="87c55-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="87c55-120">Użyj metody [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną operacją Q #:</span><span class="sxs-lookup"><span data-stu-id="87c55-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="87c55-121">Wywoływanie zasobów szacowania z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="87c55-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="87c55-122">Podczas uruchamiania programu Q # z wiersza polecenia, użyj parametru **--symulatora** (lub **-s** skrótu), aby określić `ResourcesEstimator` maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="87c55-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="87c55-123">Następujące polecenie uruchamia program przy użyciu szacowania zasobów:</span><span class="sxs-lookup"><span data-stu-id="87c55-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="87c55-124">Wywoływanie zasobów szacowania z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="87c55-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="87c55-125">Użyj polecenia IQ # Magic [% oszacowanie](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić operację Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="87c55-126">Programowe pobieranie szacowanych danych</span><span class="sxs-lookup"><span data-stu-id="87c55-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="87c55-127">Oprócz tabeli TSV można programowo pobrać zasoby szacowane podczas wykonywania przez `Data` Właściwość zasobów szacowania.</span><span class="sxs-lookup"><span data-stu-id="87c55-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="87c55-128">`Data`Właściwość zawiera `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.</span><span class="sxs-lookup"><span data-stu-id="87c55-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="87c55-129">Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` operacji oraz operacje używane przez operację Q #:</span><span class="sxs-lookup"><span data-stu-id="87c55-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="87c55-130">Zgłoszone metryki</span><span class="sxs-lookup"><span data-stu-id="87c55-130">Metrics Reported</span></span>

<span data-ttu-id="87c55-131">Szacowania zasobów śledzi następujące metryki:</span><span class="sxs-lookup"><span data-stu-id="87c55-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="87c55-132">Metryka</span><span class="sxs-lookup"><span data-stu-id="87c55-132">Metric</span></span>|<span data-ttu-id="87c55-133">Opis</span><span class="sxs-lookup"><span data-stu-id="87c55-133">Description</span></span>|
|----|----|
|<span data-ttu-id="87c55-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="87c55-134">__CNOT__</span></span>    |<span data-ttu-id="87c55-135">Liczba uruchomień `CNOT` operacji (znanych także jako kontrolowane operacje Pauli X).</span><span class="sxs-lookup"><span data-stu-id="87c55-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="87c55-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="87c55-136">__QubitClifford__</span></span> |<span data-ttu-id="87c55-137">Liczba uruchomień pojedynczego qubit Clifford i Pauli operacji.</span><span class="sxs-lookup"><span data-stu-id="87c55-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="87c55-138">__miara__</span><span class="sxs-lookup"><span data-stu-id="87c55-138">__Measure__</span></span>    |<span data-ttu-id="87c55-139">Liczba uruchomień pomiarów.</span><span class="sxs-lookup"><span data-stu-id="87c55-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="87c55-140">__R__</span><span class="sxs-lookup"><span data-stu-id="87c55-140">__R__</span></span>    |<span data-ttu-id="87c55-141">Liczba uruchomień wszystkich rotacji qubit, z wyjątkiem `T` operacji Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="87c55-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="87c55-142">__T__</span><span class="sxs-lookup"><span data-stu-id="87c55-142">__T__</span></span>    |<span data-ttu-id="87c55-143">Liczba uruchomień `T` operacji i ich sprzężenia, w tym `T` operacje, T_x = H. T. H i T_y = HY. T. HY.</span><span class="sxs-lookup"><span data-stu-id="87c55-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="87c55-144">__Ścisł__</span><span class="sxs-lookup"><span data-stu-id="87c55-144">__Depth__</span></span>|<span data-ttu-id="87c55-145">Dolna granica głębokości obwodu Quantum przebiegu przez operację Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="87c55-146">Domyślnie Metryka głębokości liczy tylko `T` bramy.</span><span class="sxs-lookup"><span data-stu-id="87c55-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="87c55-147">Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="87c55-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="87c55-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="87c55-148">__Width__</span></span>    |<span data-ttu-id="87c55-149">Dolna granica maksymalnej liczby qubits przydzieloną podczas przebiegu operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="87c55-150">Jednocześnie może nie być możliwe równoczesne osiąganie __głębokości__ i dolnej granicy __szerokości__ .</span><span class="sxs-lookup"><span data-stu-id="87c55-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="87c55-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="87c55-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="87c55-152">Maksymalna liczba qubits zaciągniętych w ramach operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="87c55-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="87c55-153">Zapewnianie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="87c55-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="87c55-154">Możesz użyć <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> przestrzeni nazw, aby podać informacje o oczekiwanym prawdopodobieństwie operacji pomiaru.</span><span class="sxs-lookup"><span data-stu-id="87c55-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="87c55-155">Aby uzyskać więcej informacji, zobacz [symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="87c55-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="87c55-156">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="87c55-156">See also</span></span>

- [<span data-ttu-id="87c55-157">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="87c55-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="87c55-158">Symulator Toffoli Quantum</span><span class="sxs-lookup"><span data-stu-id="87c55-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="87c55-159">Symulator pełnego stanu Quantum</span><span class="sxs-lookup"><span data-stu-id="87c55-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 