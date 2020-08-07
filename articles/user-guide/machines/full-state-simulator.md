---
title: Pełny stan symulatora Quantum — zestaw Quantum Development Kit
description: Dowiedz się, jak uruchamiać Q# programy na Microsoft Quantum Development Kit symulatorze stanu pełnego.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: b15af66123dadae09815cde1966c69b3ce2e9e64
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868342"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="6598b-103">Zestaw Quantum Development Kit (QDK) — symulator stanu pełnego</span><span class="sxs-lookup"><span data-stu-id="6598b-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="6598b-104">QDK zapewnia pełen symulatora stanu, który symuluje maszynę Quantum na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="6598b-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="6598b-105">Za pomocą symulatora stanu pełnego można uruchamiać i debugować algorytmy Quantum Q# , wykorzystując do 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="6598b-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="6598b-106">Pełen symulator stanu jest podobny do symulatora Quantum używanego w [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformy Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="6598b-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="6598b-107">Wywoływanie i uruchamianie symulatora stanu pełnego</span><span class="sxs-lookup"><span data-stu-id="6598b-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="6598b-108">Uwidaczniasz pełny symulator stanu za pośrednictwem `QuantumSimulator` klasy.</span><span class="sxs-lookup"><span data-stu-id="6598b-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="6598b-109">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="6598b-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="6598b-110">Wywoływanie symulatora z C #</span><span class="sxs-lookup"><span data-stu-id="6598b-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="6598b-111">Utwórz wystąpienie `QuantumSimulator` klasy, a następnie Przekaż je do `Run` metody operacji Quantum, wraz z wszelkimi dodatkowymi parametrami.</span><span class="sxs-lookup"><span data-stu-id="6598b-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="6598b-112">Ponieważ `QuantumSimulator` Klasa implementuje <xref:System.IDisposable> interfejs, należy wywołać `Dispose` metodę, gdy nie jest już potrzebne wystąpienie symulatora.</span><span class="sxs-lookup"><span data-stu-id="6598b-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="6598b-113">Najlepszym sposobem jest otoczenie deklaracji symulatora i operacji w instrukcji [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , która automatycznie wywołuje `Dispose` metodę.</span><span class="sxs-lookup"><span data-stu-id="6598b-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="6598b-114">Wywoływanie symulatora z języka Python</span><span class="sxs-lookup"><span data-stu-id="6598b-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="6598b-115">Użyj metody [symulacja ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Q# Python z zaimportowaną Q# operacją:</span><span class="sxs-lookup"><span data-stu-id="6598b-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="6598b-116">Wywoływanie symulatora z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="6598b-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="6598b-117">W przypadku uruchamiania Q# programu z wiersza polecenia symulator stanu pełni jest domyślną maszyną docelową.</span><span class="sxs-lookup"><span data-stu-id="6598b-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="6598b-118">Opcjonalnie można użyć parametru **--symulatora** (lub **-s** ), aby określić odpowiednią maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="6598b-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="6598b-119">Oba poniższe polecenia uruchamiają program przy użyciu symulatora stanu pełnego.</span><span class="sxs-lookup"><span data-stu-id="6598b-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="6598b-120">Wywoływanie symulatora z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="6598b-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="6598b-121">Użyj I Q# Magic polecenia [% symulacja](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić Q# operację.</span><span class="sxs-lookup"><span data-stu-id="6598b-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="6598b-122">Rozmieszczanie symulatora</span><span class="sxs-lookup"><span data-stu-id="6598b-122">Seeding the simulator</span></span>

<span data-ttu-id="6598b-123">Domyślnie symulator o pełnym stanie używa generatora liczb losowych do symulowania losowości Quantum.</span><span class="sxs-lookup"><span data-stu-id="6598b-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="6598b-124">W celach testowych czasami warto mieć deterministyczne wyniki.</span><span class="sxs-lookup"><span data-stu-id="6598b-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="6598b-125">W programie w języku C# można to zrobić, dostarczając inicjator dla generatora liczb losowych w `QuantumSimulator` konstruktorze za pośrednictwem `randomNumberGeneratorSeed` parametru.</span><span class="sxs-lookup"><span data-stu-id="6598b-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="6598b-126">Konfigurowanie wątków</span><span class="sxs-lookup"><span data-stu-id="6598b-126">Configuring threads</span></span>

<span data-ttu-id="6598b-127">W przypadku symulatora pełnego stanu do zrównoleglanie algebry liniowych wymagana jest funkcja [OpenMP](http://www.openmp.org/) .</span><span class="sxs-lookup"><span data-stu-id="6598b-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="6598b-128">Domyślnie OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą qubits często działają powoli, ponieważ koordynacja, która jest wymagana Dwarfs rzeczywistej pracy.</span><span class="sxs-lookup"><span data-stu-id="6598b-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="6598b-129">Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę.</span><span class="sxs-lookup"><span data-stu-id="6598b-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="6598b-130">Jako regułę elementu kciuka skonfiguruj jeden wątek dla maksymalnie czterech qubits, a następnie jeden dodatkowy wątek na qubit.</span><span class="sxs-lookup"><span data-stu-id="6598b-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="6598b-131">Może być konieczne dostosowanie zmiennej w zależności od algorytmu.</span><span class="sxs-lookup"><span data-stu-id="6598b-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="6598b-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6598b-132">See also</span></span>

- [<span data-ttu-id="6598b-133">Narzędzie do szacowania zasobów kwantowych</span><span class="sxs-lookup"><span data-stu-id="6598b-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="6598b-134">Kwantowy symulator Toffoli</span><span class="sxs-lookup"><span data-stu-id="6598b-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="6598b-135">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="6598b-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)