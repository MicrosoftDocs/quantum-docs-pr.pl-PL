---
title: Quantum Toffoli symulator — Quantum Development Kit
description: Dowiedz się więcej o symulatorze Microsoft QDK Toffoli, w specjalnym symulatorze Quantum, który może być używany z milionami qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690779"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="73601-103">Zestaw Quantum Development Kit (QDK) Toffoli symulator</span><span class="sxs-lookup"><span data-stu-id="73601-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="73601-104">Symulator QDK Toffoli jest symulatorem specjalnym z ograniczonym zakresem i obsługuje tylko `X` i obsługują `CNOT` wielokontrolowane `X` operacje Quantum.</span><span class="sxs-lookup"><span data-stu-id="73601-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="73601-105">Wszystkie klasyczne logiki i obliczenia są dostępne.</span><span class="sxs-lookup"><span data-stu-id="73601-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="73601-106">Chociaż symulator Toffoli jest bardziej ograniczony w funkcjonalności niż [symulator stanu pełnego](xref:microsoft.quantum.machines.full-state-simulator), zaletą jest możliwość symulowania znacznie większej liczby qubits.</span><span class="sxs-lookup"><span data-stu-id="73601-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="73601-107">Symulatora Toffoli można używać z milionami qubits, podczas gdy pełny symulator stanu jest ograniczony do około 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="73601-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="73601-108">Jest to przydatne, na przykład w przypadku systemów Oracle, które obliczają funkcje logiczne — można zaimplementować przy użyciu ograniczonego zestawu obsługiwanych algorytmów i przetestowanych na dużą liczbę qubits.</span><span class="sxs-lookup"><span data-stu-id="73601-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="73601-109">Wywoływanie symulatora Toffoli</span><span class="sxs-lookup"><span data-stu-id="73601-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="73601-110">Symulator Toffoli można uwidocznić za pośrednictwem `ToffoliSimulator` klasy.</span><span class="sxs-lookup"><span data-stu-id="73601-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="73601-111">Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="73601-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="73601-112">Wywoływanie symulatora Toffoli z języka C #</span><span class="sxs-lookup"><span data-stu-id="73601-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="73601-113">Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `ToffoliSimulator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.</span><span class="sxs-lookup"><span data-stu-id="73601-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="73601-114">Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `ToffoliSimulator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="73601-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="73601-115">Wywoływanie symulatora Toffoli z poziomu języka Python</span><span class="sxs-lookup"><span data-stu-id="73601-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="73601-116">Użyj metody [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną Q# operacją:</span><span class="sxs-lookup"><span data-stu-id="73601-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="73601-117">Wywoływanie symulatora Toffoli z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="73601-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="73601-118">Podczas uruchamiania Q# programu z wiersza polecenia, użyj parametru **--symulatora** (lub **-s** skrótu), aby określić komputer docelowy symulatora Toffoli.</span><span class="sxs-lookup"><span data-stu-id="73601-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="73601-119">Następujące polecenie uruchamia program przy użyciu szacowania zasobów:</span><span class="sxs-lookup"><span data-stu-id="73601-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="73601-120">Wywoływanie symulatora Toffoli z notesów Juptyer</span><span class="sxs-lookup"><span data-stu-id="73601-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="73601-121">Użyj I Q# Magic polecenia [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) , aby uruchomić Q# operację.</span><span class="sxs-lookup"><span data-stu-id="73601-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="73601-122">Obsługiwane operacje</span><span class="sxs-lookup"><span data-stu-id="73601-122">Supported operations</span></span>

<span data-ttu-id="73601-123">Symulator Toffoli obsługuje:</span><span class="sxs-lookup"><span data-stu-id="73601-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="73601-124">Rotacje i exponentiated Pauly, takie jak `R` i `Exp` , gdy wynikiem operacji jest równa `X` się lub macierzy tożsamości.</span><span class="sxs-lookup"><span data-stu-id="73601-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="73601-125">Operacje pomiarów i [potwierdzeń](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) , ale tylko na `Z` podstawie Pauli.</span><span class="sxs-lookup"><span data-stu-id="73601-125">Measurement and [assert](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="73601-126">Zwróć uwagę, że prawdopodobieństwo operacji pomiaru ma zawsze **wartość 0** lub **1** ; nie ma losowości w symulatorze Toffoli.</span><span class="sxs-lookup"><span data-stu-id="73601-126">Note that a measurement operation's probability is always either **0** or **1** ; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="73601-127">`DumpMachine` i `DumpRegister` funkcje.</span><span class="sxs-lookup"><span data-stu-id="73601-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="73601-128">Obie funkcje wyprowadzają bieżący `Z` stan bazowy każdego qubitu, jedną qubit na wiersz.</span><span class="sxs-lookup"><span data-stu-id="73601-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="73601-129">Określanie liczby qubits</span><span class="sxs-lookup"><span data-stu-id="73601-129">Specifying the number of qubits</span></span>

<span data-ttu-id="73601-130">Domyślnie `ToffoliSimulator` wystąpienie przydziela miejsce na 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="73601-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="73601-131">Jeśli algorytm wymaga więcej qubits niż ten, można określić liczbę qubit, podając wartość `qubitCount` parametru do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="73601-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="73601-132">Każdy dodatkowy qubit wymaga tylko jednego bajtu pamięci, więc nie ma znaczącego kosztu oszacowania liczby potrzebnych qubits.</span><span class="sxs-lookup"><span data-stu-id="73601-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="73601-133">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="73601-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="73601-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73601-134">See also</span></span>

- [<span data-ttu-id="73601-135">Szacowania zasobów Quantum</span><span class="sxs-lookup"><span data-stu-id="73601-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="73601-136">Symulator śledzenia Quantum</span><span class="sxs-lookup"><span data-stu-id="73601-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="73601-137">Symulator pełnego stanu Quantum</span><span class="sxs-lookup"><span data-stu-id="73601-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 