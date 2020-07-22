---
title: Pełny stan symulatora Quantum — zestaw Quantum Development Kit
description: 'Dowiedz się, jak uruchamiać programy Q # na Microsoft Quantum Development Kit symulatorze pełnego stanu.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871182"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="df61f-103">Zestaw Quantum Development Kit (QDK) — symulator stanu pełnego</span><span class="sxs-lookup"><span data-stu-id="df61f-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="df61f-104">QDK zapewnia pełen symulatora stanu, który symuluje maszynę Quantum na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="df61f-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="df61f-105">Za pomocą symulatora stanu pełnego można uruchamiać i debugować algorytmy Quantum w języku Q #, wykorzystując do 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="df61f-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="df61f-106">Pełen symulator stanu jest podobny do symulatora Quantum używanego w [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformy Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="df61f-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="df61f-107">Wywoływanie i uruchamianie symulatora stanu pełnego</span><span class="sxs-lookup"><span data-stu-id="df61f-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="df61f-108">Uwidaczniasz pełny symulator stanu za pośrednictwem `QuantumSimulator` klasy.</span><span class="sxs-lookup"><span data-stu-id="df61f-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="df61f-109">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania programu Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="df61f-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="df61f-110">Wywoływanie symulatora z C #</span><span class="sxs-lookup"><span data-stu-id="df61f-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="df61f-111">Utwórz wystąpienie `QuantumSimulator` klasy, a następnie Przekaż je do `Run` metody operacji Quantum, wraz z wszelkimi dodatkowymi parametrami.</span><span class="sxs-lookup"><span data-stu-id="df61f-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="df61f-112">Ponieważ `QuantumSimulator` Klasa implementuje <xref:System.IDisposable> interfejs, należy wywołać `Dispose` metodę, gdy nie jest już potrzebne wystąpienie symulatora.</span><span class="sxs-lookup"><span data-stu-id="df61f-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="df61f-113">Najlepszym sposobem jest otoczenie deklaracji symulatora i operacji w instrukcji [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , która automatycznie wywołuje `Dispose` metodę.</span><span class="sxs-lookup"><span data-stu-id="df61f-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="df61f-114">Wywoływanie symulatora z języka Python</span><span class="sxs-lookup"><span data-stu-id="df61f-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="df61f-115">Użyj metody [symulacja ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Python q # z zaimportowaną operacją q #:</span><span class="sxs-lookup"><span data-stu-id="df61f-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="df61f-116">Wywoływanie symulatora z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="df61f-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="df61f-117">W przypadku uruchamiania programu Q # z wiersza polecenia symulator stanu pełnego jest domyślną maszyną docelową.</span><span class="sxs-lookup"><span data-stu-id="df61f-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="df61f-118">Opcjonalnie można użyć parametru **--symulatora** (lub **-s** ), aby określić odpowiednią maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="df61f-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="df61f-119">Oba poniższe polecenia uruchamiają program przy użyciu symulatora stanu pełnego.</span><span class="sxs-lookup"><span data-stu-id="df61f-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="df61f-120">Wywoływanie symulatora z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="df61f-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="df61f-121">Użyj polecenia IQ # Magic [% symulacja](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić operację Q #.</span><span class="sxs-lookup"><span data-stu-id="df61f-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="df61f-122">Rozmieszczanie symulatora</span><span class="sxs-lookup"><span data-stu-id="df61f-122">Seeding the simulator</span></span>

<span data-ttu-id="df61f-123">Domyślnie symulator o pełnym stanie używa generatora liczb losowych do symulowania losowości Quantum.</span><span class="sxs-lookup"><span data-stu-id="df61f-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="df61f-124">W celach testowych czasami warto mieć deterministyczne wyniki.</span><span class="sxs-lookup"><span data-stu-id="df61f-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="df61f-125">W programie w języku C# można to zrobić, dostarczając inicjator dla generatora liczb losowych w `QuantumSimulator` konstruktorze za pośrednictwem `randomNumberGeneratorSeed` parametru.</span><span class="sxs-lookup"><span data-stu-id="df61f-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="df61f-126">Konfigurowanie wątków</span><span class="sxs-lookup"><span data-stu-id="df61f-126">Configuring threads</span></span>

<span data-ttu-id="df61f-127">W przypadku symulatora pełnego stanu do zrównoleglanie algebry liniowych wymagana jest funkcja [OpenMP](http://www.openmp.org/) .</span><span class="sxs-lookup"><span data-stu-id="df61f-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="df61f-128">Domyślnie OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą qubits często działają powoli, ponieważ koordynacja, która jest wymagana Dwarfs rzeczywistej pracy.</span><span class="sxs-lookup"><span data-stu-id="df61f-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="df61f-129">Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę.</span><span class="sxs-lookup"><span data-stu-id="df61f-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="df61f-130">Jako regułę elementu kciuka skonfiguruj jeden wątek dla maksymalnie czterech qubits, a następnie jeden dodatkowy wątek na qubit.</span><span class="sxs-lookup"><span data-stu-id="df61f-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="df61f-131">Może być konieczne dostosowanie zmiennej w zależności od algorytmu.</span><span class="sxs-lookup"><span data-stu-id="df61f-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="df61f-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="df61f-132">See also</span></span>

- [<span data-ttu-id="df61f-133">Szacowania zasobów Quantum</span><span class="sxs-lookup"><span data-stu-id="df61f-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="df61f-134">Symulator Toffoli Quantum</span><span class="sxs-lookup"><span data-stu-id="df61f-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="df61f-135">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="df61f-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)