---
title: Symulator stanu pełnego
description: 'Dowiedz się, jak uruchamiać programy Q # na Microsoft Quantum Development Kit symulatorze pełnego stanu.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906121"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="05318-103">Symulator trybu pełnego stanu zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="05318-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="05318-104">Zestaw Quantum Development Kit zawiera pełny stan symulatora Quantum podobny do [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) from Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="05318-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="05318-105">Ten symulator może służyć do wykonywania i debugowania algorytmów Quantum, które są zapisywane w Q # na komputerze.</span><span class="sxs-lookup"><span data-stu-id="05318-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="05318-106">Ten symulator Quantum jest udostępniany za pośrednictwem klasy `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="05318-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="05318-107">Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do metody `Run` operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:</span><span class="sxs-lookup"><span data-stu-id="05318-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="05318-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="05318-108">IDisposable</span></span>

<span data-ttu-id="05318-109">Klasa `QuantumSimulator` implementuje <xref:System.IDisposable>, dlatego Metoda `Dispose` powinna być wywoływana, gdy wystąpienie symulatora nie jest już używane.</span><span class="sxs-lookup"><span data-stu-id="05318-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="05318-110">Najlepszym sposobem jest otoczenie symulatora w instrukcji `using`, jak w powyższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="05318-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="05318-111">sadzenia</span><span class="sxs-lookup"><span data-stu-id="05318-111">Seed</span></span>

<span data-ttu-id="05318-112">`QuantumSimulator` używa generatora liczb losowych w celu symulowania losowości Quantum.</span><span class="sxs-lookup"><span data-stu-id="05318-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="05318-113">W celach testowych czasami warto mieć deterministyczne wyniki.</span><span class="sxs-lookup"><span data-stu-id="05318-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="05318-114">Można to osiągnąć przez udostępnienie inicjatora dla generatora liczb losowych w konstruktorze `QuantumSimulator`za pośrednictwem parametru `randomNumberGeneratorSeed`:</span><span class="sxs-lookup"><span data-stu-id="05318-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="05318-115">Wątki</span><span class="sxs-lookup"><span data-stu-id="05318-115">Threads</span></span>

<span data-ttu-id="05318-116">`QuantumSimulator` używa [OpenMP](http://www.openmp.org/) do zrównoleglanie algebry liniowy.</span><span class="sxs-lookup"><span data-stu-id="05318-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="05318-117">Domyślnie interfejs OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą kubitów często działają wolniej, ponieważ wymóg koordynacji powoduje spowolnienie rzeczywistej pracy.</span><span class="sxs-lookup"><span data-stu-id="05318-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="05318-118">Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę.</span><span class="sxs-lookup"><span data-stu-id="05318-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="05318-119">Można kierować się zasadą, że w przybliżeniu 1 wątek jest wystarczający dla około 4 kubitów. Następnie na jeden kubit powinien przypadać jeden dodatkowy wątek. Jest to jednak szacowanie wysoce zależne od konkretnego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="05318-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

