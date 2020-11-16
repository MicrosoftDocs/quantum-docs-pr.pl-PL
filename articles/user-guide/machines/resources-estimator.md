---
title: Zasoby Quantum szacowania-Quantum Development Kit
description: 'Dowiedz się więcej o programie Microsoft QDKe szacowania, który szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e1ec01d85a141b9c8a7a5ba5589663a0773520e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691871"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="344ba-103">Zasoby zestawu Quantum Development Kit (QDK) szacowania</span><span class="sxs-lookup"><span data-stu-id="344ba-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="344ba-104">Jak nazwa oznacza, `ResourcesEstimator` Klasa szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="344ba-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="344ba-105">Jest to wykonywane przez uruchomienie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu szacuje zasoby dla Q# operacji, które korzystają z tysięcy qubits, pod warunkiem, że klasyczna część kodu jest uruchamiana w rozsądnym czasie.</span><span class="sxs-lookup"><span data-stu-id="344ba-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="344ba-106">Szacowania zasobów jest oparty na [symulatorze śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), który zapewnia bogatszy zestaw metryk i narzędzi ułatwiających debugowanie Q# programów.</span><span class="sxs-lookup"><span data-stu-id="344ba-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="344ba-107">Wywoływanie i uruchamianie zasobów szacowania</span><span class="sxs-lookup"><span data-stu-id="344ba-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="344ba-108">Możesz użyć szacowania zasobów do uruchomienia dowolnej Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="344ba-109">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="344ba-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="344ba-110">Wywoływanie zasobów szacowania z języka C #</span><span class="sxs-lookup"><span data-stu-id="344ba-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="344ba-111">Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `ResourceEstimator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.</span><span class="sxs-lookup"><span data-stu-id="344ba-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="344ba-112">Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `ResourceEstimator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="344ba-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="344ba-113">Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę, która generuje tabelę z wartościami rozdzielonymi tabulatorami (tsv).</span><span class="sxs-lookup"><span data-stu-id="344ba-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="344ba-114">Tabelę można zapisać w pliku lub wyświetlić w konsoli programu na potrzeby analizy.</span><span class="sxs-lookup"><span data-stu-id="344ba-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="344ba-115">Poniżej przedstawiono przykładowe dane wyjściowe z poprzedniego programu:</span><span class="sxs-lookup"><span data-stu-id="344ba-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="344ba-116">`ResourcesEstimator`Wystąpienie nie resetuje obliczeń dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="344ba-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="344ba-117">Jeśli używasz tego samego wystąpienia do uruchomienia innej operacji, agreguje nowe wyniki z istniejącymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="344ba-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="344ba-118">Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego przebiegu.</span><span class="sxs-lookup"><span data-stu-id="344ba-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="344ba-119">Wywoływanie zasobów szacowania z języka Python</span><span class="sxs-lookup"><span data-stu-id="344ba-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="344ba-120">Użyj metody [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną Q# operacją:</span><span class="sxs-lookup"><span data-stu-id="344ba-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="344ba-121">Wywoływanie zasobów szacowania z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="344ba-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="344ba-122">Podczas uruchamiania Q# programu z wiersza polecenia należy użyć parametru **--symulatora** (lub **-s** ), aby określić `ResourcesEstimator` maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="344ba-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="344ba-123">Następujące polecenie uruchamia program przy użyciu szacowania zasobów:</span><span class="sxs-lookup"><span data-stu-id="344ba-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="344ba-124">Wywoływanie zasobów szacowania z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="344ba-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="344ba-125">Q#Aby uruchomić operację, użyj polecenia I [oszacowania% oszacowanie](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .</span><span class="sxs-lookup"><span data-stu-id="344ba-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="344ba-126">Programowe pobieranie szacowanych danych</span><span class="sxs-lookup"><span data-stu-id="344ba-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="344ba-127">Oprócz tabeli TSV można programowo pobrać zasoby szacowane podczas wykonywania przez `Data` Właściwość zasobów szacowania.</span><span class="sxs-lookup"><span data-stu-id="344ba-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="344ba-128">`Data`Właściwość zawiera `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.</span><span class="sxs-lookup"><span data-stu-id="344ba-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="344ba-129">Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` operacji oraz operacje wykonywane przez Q# operację:</span><span class="sxs-lookup"><span data-stu-id="344ba-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="344ba-130">Zgłoszone metryki</span><span class="sxs-lookup"><span data-stu-id="344ba-130">Metrics Reported</span></span>

<span data-ttu-id="344ba-131">Szacowania zasobów śledzi następujące metryki:</span><span class="sxs-lookup"><span data-stu-id="344ba-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="344ba-132">Metryka</span><span class="sxs-lookup"><span data-stu-id="344ba-132">Metric</span></span>|<span data-ttu-id="344ba-133">Opis</span><span class="sxs-lookup"><span data-stu-id="344ba-133">Description</span></span>|
|----|----|
|<span data-ttu-id="344ba-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="344ba-134">__CNOT__</span></span>    |<span data-ttu-id="344ba-135">Liczba uruchomień `CNOT` operacji (znanych także jako kontrolowane operacje Pauli X).</span><span class="sxs-lookup"><span data-stu-id="344ba-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="344ba-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="344ba-136">__QubitClifford__</span></span> |<span data-ttu-id="344ba-137">Liczba uruchomień pojedynczego qubit Clifford i Pauli operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="344ba-138">__Miara__</span><span class="sxs-lookup"><span data-stu-id="344ba-138">__Measure__</span></span>    |<span data-ttu-id="344ba-139">Liczba uruchomień pomiarów.</span><span class="sxs-lookup"><span data-stu-id="344ba-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="344ba-140">__R__</span><span class="sxs-lookup"><span data-stu-id="344ba-140">__R__</span></span>    |<span data-ttu-id="344ba-141">Liczba uruchomień wszystkich rotacji qubit, z wyjątkiem `T` operacji Clifford i Pauli.</span><span class="sxs-lookup"><span data-stu-id="344ba-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="344ba-142">__T__</span><span class="sxs-lookup"><span data-stu-id="344ba-142">__T__</span></span>    |<span data-ttu-id="344ba-143">Liczba uruchomień `T` operacji i ich sprzężenia, w tym `T` operacje, T_x = H. T. H i T_y = HY. T. HY.</span><span class="sxs-lookup"><span data-stu-id="344ba-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="344ba-144">__Ścisł__</span><span class="sxs-lookup"><span data-stu-id="344ba-144">__Depth__</span></span>|<span data-ttu-id="344ba-145">Głębokość obwodu Quantum uruchamianego przez Q# operację (patrz [poniżej](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="344ba-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="344ba-146">Domyślnie Metryka głębokości liczy tylko `T` bramy.</span><span class="sxs-lookup"><span data-stu-id="344ba-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="344ba-147">Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="344ba-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="344ba-148">__Szerokość__</span><span class="sxs-lookup"><span data-stu-id="344ba-148">__Width__</span></span>|<span data-ttu-id="344ba-149">Szerokość obwodu Quantum uruchamianego przez Q# operację (patrz [poniżej](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="344ba-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="344ba-150">Domyślnie Metryka głębokości liczy tylko `T` bramy.</span><span class="sxs-lookup"><span data-stu-id="344ba-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="344ba-151">Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="344ba-151">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="344ba-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="344ba-152">__QubitCount__</span></span>    |<span data-ttu-id="344ba-153">Dolna granica maksymalnej liczby qubits przydzieloną podczas uruchamiania Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="344ba-154">Ta Metryka może nie być zgodna z __głębokością__ (patrz poniżej).</span><span class="sxs-lookup"><span data-stu-id="344ba-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="344ba-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="344ba-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="344ba-156">Maksymalna liczba qubits zaciągniętych w ramach Q# operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="344ba-157">Głębokość, Szerokość i QubitCount</span><span class="sxs-lookup"><span data-stu-id="344ba-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="344ba-158">Raportowane oszacowania głębokości i szerokości są zgodne ze sobą.</span><span class="sxs-lookup"><span data-stu-id="344ba-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="344ba-159">(Poprzednio obie liczby były osiągalne, ale na potrzeby głębokości i szerokości są wymagane różne obwody.) Obecnie obie metryki w tej parze mogą być osiągane przez ten sam obwód w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="344ba-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="344ba-160">Zgłaszane są następujące metryki:</span><span class="sxs-lookup"><span data-stu-id="344ba-160">The following metrics are reported:</span></span>

<span data-ttu-id="344ba-161">__Głębokość:__ W przypadku operacji głównej należy wykonać ją w celu jej wykonania przy założeniu określonych czasów bramy.</span><span class="sxs-lookup"><span data-stu-id="344ba-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="344ba-162">Dla operacji o nazwie lub późniejszych wartościach czasowych między najnowszym czasem dostępności qubit na początku i na końcu operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="344ba-163">__Szerokość:__ W przypadku operacji głównej — liczba qubits rzeczywiście użyta do jej wykonania (i operacji wywoływanych przez nią).</span><span class="sxs-lookup"><span data-stu-id="344ba-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="344ba-164">W przypadku operacji o wartościach lub kolejnych operacjach — ile więcej qubits było używanych oprócz qubits już używanych na początku operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="344ba-165">Należy pamiętać, że ponownie użyte qubits nie przyczyniają się do tej liczby.</span><span class="sxs-lookup"><span data-stu-id="344ba-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="344ba-166">Oznacza to, że jeśli kilka qubits zostało zwolnionych przed rozpoczęciem operacji i wszystkie qubit wymagane przez tę operację a (i operacje wywoływane z) zostały spełnione przez ponowne użycie poprzednio wydanej wersji qubits, Szerokość operacji A jest raportowana jako 0.</span><span class="sxs-lookup"><span data-stu-id="344ba-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="344ba-167">Pomyślnie pożyczone qubits nie przyczyniają się do szerokości.</span><span class="sxs-lookup"><span data-stu-id="344ba-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="344ba-168">__QubitCount:__ W przypadku operacji głównej — minimalna liczba qubits, które byłyby wystarczające do wykonania tej operacji (i wywoływanej z niej operacji).</span><span class="sxs-lookup"><span data-stu-id="344ba-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="344ba-169">W przypadku operacji o nazwie lub kolejnych operacji — minimalna liczba qubits, które byłyby wystarczające do wykonania tej operacji osobno.</span><span class="sxs-lookup"><span data-stu-id="344ba-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="344ba-170">Ta liczba nie zawiera qubits danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="344ba-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="344ba-171">Obejmuje to zapożyczone qubits.</span><span class="sxs-lookup"><span data-stu-id="344ba-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="344ba-172">Obsługiwane są dwa tryby operacji.</span><span class="sxs-lookup"><span data-stu-id="344ba-172">Two modes of operation are supported.</span></span> <span data-ttu-id="344ba-173">Tryb jest wybierany przez ustawienie QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="344ba-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="344ba-174">__OptimizeDepth = true:__ Nie zaleca się QubitManager z qubit ponownie i przydziela nowe qubit za każdym razem, gdy zostanie wyświetlony monit o qubit.</span><span class="sxs-lookup"><span data-stu-id="344ba-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="344ba-175">Dla __głębokości__ operacji głównej jest to minimalna głębokość (Dolna granica).</span><span class="sxs-lookup"><span data-stu-id="344ba-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="344ba-176">Dla tej głębokości zgłoszono zgodną __Szerokość__ (obie można osiągnąć w tym samym czasie).</span><span class="sxs-lookup"><span data-stu-id="344ba-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="344ba-177">Należy zauważyć, że ta szerokość prawdopodobnie nie będzie optymalna.</span><span class="sxs-lookup"><span data-stu-id="344ba-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="344ba-178">Wartość __QubitCount__ może być mniejsza niż szerokość operacji głównej, ponieważ zakłada się jej ponowne użycie.</span><span class="sxs-lookup"><span data-stu-id="344ba-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="344ba-179">__OptimizeDepth = FAŁSZ:__ QubitManager zaleca się ponowne użycie qubits i ponowne użycie zwolnienia qubits przed przydzieleniem nowych.</span><span class="sxs-lookup"><span data-stu-id="344ba-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="344ba-180">__Szerokość__ operacji głównej jest minimalna (Dolna granica).</span><span class="sxs-lookup"><span data-stu-id="344ba-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="344ba-181">Jest raportowana zgodna __głębokość__ , na której można ją osiągnąć.</span><span class="sxs-lookup"><span data-stu-id="344ba-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="344ba-182">__QubitCount__ będzie taka sama jak __Szerokość__ dla operacji głównej, przy założeniu, że nie pożyczy się.</span><span class="sxs-lookup"><span data-stu-id="344ba-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="344ba-183">Podawanie prawdopodobieństwa wyników pomiarów</span><span class="sxs-lookup"><span data-stu-id="344ba-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="344ba-184">Możesz użyć <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw, aby podać informacje o oczekiwanym prawdopodobieństwie operacji pomiaru.</span><span class="sxs-lookup"><span data-stu-id="344ba-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="344ba-185">Aby uzyskać więcej informacji, zobacz [symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="344ba-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="344ba-186">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="344ba-186">See also</span></span>

- [<span data-ttu-id="344ba-187">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="344ba-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="344ba-188">Kwantowy symulator Toffoli</span><span class="sxs-lookup"><span data-stu-id="344ba-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="344ba-189">Kwantowy symulator pełnego stanu</span><span class="sxs-lookup"><span data-stu-id="344ba-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
