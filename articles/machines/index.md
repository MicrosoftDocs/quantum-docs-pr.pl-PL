---
title: Symulatory kwantowe i sterowniki klasyczne | Microsoft Docs
description: Opis tworzenia symulatorów kwantowych przy użyciu klasycznego języka platformy .NET (zazwyczaj C# lub Q#).
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 5ac79280669ae0acfe993a1c2ae1c069b0c01848
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035117"
---
# <a name="classical-drivers-and-machines"></a><span data-ttu-id="b4d5b-103">Klasyczne sterowniki i komputery</span><span class="sxs-lookup"><span data-stu-id="b4d5b-103">Classical Drivers and Machines</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="b4d5b-104">Zawartość</span><span class="sxs-lookup"><span data-stu-id="b4d5b-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b4d5b-105">Jak są wykonywane algorytmy kwantowe</span><span class="sxs-lookup"><span data-stu-id="b4d5b-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="b4d5b-106">Jakie symulatory kwantowe są zawarte w tej wersji</span><span class="sxs-lookup"><span data-stu-id="b4d5b-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="b4d5b-107">Jak napisać sterownik C# dla algorytmu kwantowego</span><span class="sxs-lookup"><span data-stu-id="b4d5b-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="b4d5b-108">Model wykonywania zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="b4d5b-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="b4d5b-109">W artykule [Pisanie programu kwantowego](xref:microsoft.quantum.write-program) algorytm kwantowy był wykonywany przez przekazanie obiektu `QuantumSimulator` do metody `Run` klasy algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="b4d5b-110">Klasa `QuantumSimulator` umożliwia wykonanie algorytmu kwantowego dzięki pełnej symulacji wektora stanu kwantowego, który doskonale nadaje się do uruchamiania i testowania przykładu `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="b4d5b-111">Aby uzyskać więcej informacji na temat wektorów stanów kwantowych, zobacz [Przewodnik po pojęciach](xref:microsoft.quantum.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="b4d5b-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="b4d5b-112">Algorytm kwantowy można uruchamiać na innych maszynach docelowych.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="b4d5b-113">Maszyna zapewnia implementacje kwantowych typów pierwotnych algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="b4d5b-114">Obejmują one operacje pierwotne, takie jak H, CNOT i Measure, a także śledzenie kubitów i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="b4d5b-115">Poszczególne klasy maszyn kwantowych reprezentują różne modele wykonywania tego samego algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="b4d5b-116">Każdy typ maszyny kwantowej może udostępniać odrębną implementację typów pierwotnych.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="b4d5b-117">Na przykład zawarty w zestawie deweloperskim symulator śledzenia komputera kwantowego nie służy do wykonywania symulacji.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="b4d5b-118">Zamiast tego śledzi on użycie bramy, kubitów oraz innych zasobów.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="b4d5b-119">Maszyny kwantowe</span><span class="sxs-lookup"><span data-stu-id="b4d5b-119">Quantum Machines</span></span>

<span data-ttu-id="b4d5b-120">W przyszłości zostaną zdefiniowane dodatkowe klasy maszyn kwantowych umożliwiające obsługę innych typów symulacji oraz wykonywanie na topologicznych komputerach kwantowych.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="b4d5b-121">Zapewnienie niezmienności algorytmu przy różnych bazowych implementacjach na maszynach ułatwia jego testowanie i debugowanie w symulacji, a następnie uruchamianie na używanym komputerze z poczuciem pewności, że nie został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="b4d5b-122">Zawartość tej wersji</span><span class="sxs-lookup"><span data-stu-id="b4d5b-122">What's Included in this Release</span></span>

<span data-ttu-id="b4d5b-123">Ta wersja zestawu Quantum Development Kit zawiera kilka klas maszyn kwantowych.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="b4d5b-124">Każda klasa jest zdefiniowana w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="b4d5b-125">Klasa `QuantumSimulator`, [symulator wektora pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator).</span><span class="sxs-lookup"><span data-stu-id="b4d5b-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="b4d5b-126">Klasa `ResourcesEstimator`, [proste narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator), umożliwia ogólną analizę zasobów wymaganych do uruchomienia algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="b4d5b-127">Klasa `QCTraceSimulator`, [oparte na śledzeniu narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.qc-trace-simulator.intro), umożliwia zaawansowaną analizę zużycia zasobów dla całego grafu wywołań algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="b4d5b-128">Klasa `ToffoliSimulator`, [symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).</span><span class="sxs-lookup"><span data-stu-id="b4d5b-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-classical-driver-program"></a><span data-ttu-id="b4d5b-129">Pisanie klasycznego programu sterującego</span><span class="sxs-lookup"><span data-stu-id="b4d5b-129">Writing a Classical Driver Program</span></span>

<span data-ttu-id="b4d5b-130">W artykule [Pisanie programu kwantowego](xref:microsoft.quantum.write-program) napisaliśmy prosty sterownik w języku C# dla algorytmu teleportacji.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="b4d5b-131">Sterownik w języku C# ma 4 główne funkcje:</span><span class="sxs-lookup"><span data-stu-id="b4d5b-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="b4d5b-132">Konstruowanie maszyny docelowej</span><span class="sxs-lookup"><span data-stu-id="b4d5b-132">Constructing the target machine</span></span>
* <span data-ttu-id="b4d5b-133">Obliczanie wszystkich argumentów wymaganych przez algorytm kwantowy</span><span class="sxs-lookup"><span data-stu-id="b4d5b-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="b4d5b-134">Uruchamianie algorytmu kwantowego przy użyciu symulatora</span><span class="sxs-lookup"><span data-stu-id="b4d5b-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="b4d5b-135">Przetwarzanie wyniku operacji</span><span class="sxs-lookup"><span data-stu-id="b4d5b-135">Processing the result of the operation</span></span>

<span data-ttu-id="b4d5b-136">Poniżej szczegółowo omówiono poszczególne etapy.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="b4d5b-137">Konstruowanie maszyny docelowej</span><span class="sxs-lookup"><span data-stu-id="b4d5b-137">Constructing the Target Machine</span></span>

<span data-ttu-id="b4d5b-138">Maszyny kwantowe to normalne wystąpienia klas .NET, dlatego tworzy się je przez wywołanie konstruktora, tak jak w przypadku dowolnej klasy .NET.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="b4d5b-139">Niektóre symulatory, w tym `QuantumSimulator`, implementują interfejs .NET <xref:System.IDisposable?displayProperty=nameWithType>, dlatego należy je umieścić w instrukcji `using` języka C#.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="b4d5b-140">Obliczanie argumentów dla algorytmu</span><span class="sxs-lookup"><span data-stu-id="b4d5b-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="b4d5b-141">W naszym przykładzie `Teleport` obliczyliśmy kilka względnie sztucznych argumentów przekazywanych do algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="b4d5b-142">Zwykle jednak algorytm kwantowy wymaga znacznej ilości danych i najłatwiej je udostępnić z poziomu klasycznego sterownika.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="b4d5b-143">Na przykład w przypadku symulacji chemicznych algorytm kwantowy wymaga dużej tabeli wartości całkowitych dotyczących orbitalnych interakcji molekuł.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="b4d5b-144">Zazwyczaj informacje te są odczytywane z pliku, który jest dostarczany podczas uruchamiania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="b4d5b-145">Język Q# nie udostępnia mechanizmu uzyskiwania dostępu do systemu plików, dlatego najlepiej jest zebrać takie dane przy użyciu klasycznego sterownika, a następnie przekazać je do metody `Run` algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="b4d5b-146">Klasyczny sterownik odgrywa również kluczową rolę w metodach zmiennych.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="b4d5b-147">W tej klasie algorytmów na podstawie klasycznych parametrów przygotowuje się stan kwantowy, a następnie używa się go do obliczenia jakiejś wartości.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="b4d5b-148">Parametry są dostosowywane na podstawie określonego algorytmu wspinaczki lub algorytmu uczenia maszynowego, a następnie algorytm kwantowy jest uruchamiany ponownie.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="b4d5b-149">Algorytm wspinaczki najlepiej jest zaimplementować jako czysto klasyczną funkcję, wywoływaną przez klasyczny sterownik. Wyniki procesu wspinaczki są następnie przekazywane do następnego przebiegu algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="b4d5b-150">Uruchamianie algorytmu kwantowego</span><span class="sxs-lookup"><span data-stu-id="b4d5b-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="b4d5b-151">Ta część jest ogólnie bardzo prosta.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="b4d5b-152">Każda operacja języka Q# jest powiązana ze skompilowaną klasą, która udostępnia metodę statyczną `Run`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="b4d5b-153">Argumenty tej metody są udostępniane przez spłaszczoną krotkę argumentów samej operacji. Dodatkowy, pierwszy argument jest symulatorem umożliwiającym wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="b4d5b-154">Spłaszczony odpowiednik operacji, która oczekuje nazwanej krotki typu `(a: String, (b: Double, c: Double))`, to `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="b4d5b-155">Przekazując argumenty do metody `Run`, trzeba pamiętać o kilku kwestiach:</span><span class="sxs-lookup"><span data-stu-id="b4d5b-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="b4d5b-156">Tablice muszą być opakowane w obiekt `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="b4d5b-157">Klasa `QArray` ma konstruktor, który przyjmuje dowolną uporządkowaną kolekcję (`IEnumerable<T>`) odpowiednich obiektów.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="b4d5b-158">Pusta krotka, `()` w języku Q#, jest reprezentowana przez element `QVoid.Instance` w języku C#.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="b4d5b-159">Niepuste krotki są reprezentowane jako wystąpienia `ValueType` programu .NET.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-159">Non-empty tuples are represented as .NET `ValueType` instances.</span></span>
* <span data-ttu-id="b4d5b-160">Zdefiniowane przez użytkownika typy języka Q# są przekazywane jako typy podstawowe.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="b4d5b-161">Aby przekazać operację lub funkcję do metody `Run`, należy uzyskać wystąpienie klasy operacji lub funkcji przy użyciu metody `Get<>` symulatora.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="b4d5b-162">Przetwarzanie wyników</span><span class="sxs-lookup"><span data-stu-id="b4d5b-162">Processing the Results</span></span>

<span data-ttu-id="b4d5b-163">Wyniki algorytmu kwantowego są zwracane z metody `Run`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="b4d5b-164">Metoda `Run` jest wykonywana asynchronicznie, dlatego zwraca wystąpienie klasy <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="b4d5b-165">Istnieje wiele sposobów uzyskiwania rzeczywistych wyników operacji.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="b4d5b-166">Najprostszym z nich jest użycie właściwości [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) klasy `Task`:</span><span class="sxs-lookup"><span data-stu-id="b4d5b-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="b4d5b-167">Można jednak użyć innych technik, takich jak użycie metody [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) lub słowa kluczowego [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) języka C#.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="b4d5b-168">Podobnie jak w przypadku argumentów, krotki języka Q# są reprezentowane jako wystąpienia `ValueTuple`, a tablice języka Q# są reprezentowane jako wystąpienia `QArray`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="b4d5b-169">Typy zdefiniowane przez użytkownika są zwracane jako typy podstawowe.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="b4d5b-170">Pusta krotka `()` jest zwracana jako wystąpienie klasy `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="b4d5b-171">Wiele algorytmów kwantowych wymaga rozbudowanego przetwarzania końcowego w celu uzyskania użytecznych odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="b4d5b-172">Na przykład kwantowa część algorytmu Shora jest tylko początkiem obliczeń, które umożliwiają rozłożenie liczby na czynniki.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="b4d5b-173">W większości przypadków takie przetwarzanie końcowe najłatwiej jest zrealizować w klasycznym sterowniku.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="b4d5b-174">Udostępnienie wyników użytkownikowi lub zapisanie ich na dysku jest możliwe tylko za pomocą klasycznego sterownika.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="b4d5b-175">Klasyczny sterownik ma dostęp do bibliotek analitycznych i innych funkcji matematycznych, które nie są dostępne w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="b4d5b-176">Błędy</span><span class="sxs-lookup"><span data-stu-id="b4d5b-176">Failures</span></span>

<span data-ttu-id="b4d5b-177">Gdy podczas operacji nastąpi wykonywanie instrukcji `fail` języka Q#, zostanie zgłoszony wyjątek `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="b4d5b-178">Ze względu na użycie klasy `System.Task` w metodzie `Run` wyjątek zgłoszony w wyniku instrukcji `fail` zostanie opakowany w klasę `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="b4d5b-179">Aby znaleźć faktyczną przyczynę błędu, należy wykonać iterację we właściwości `AggregateException` 
`InnerExceptions`, na przykład:</span><span class="sxs-lookup"><span data-stu-id="b4d5b-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="b4d5b-180">Inne języki klasyczne</span><span class="sxs-lookup"><span data-stu-id="b4d5b-180">Other Classical Languages</span></span>

<span data-ttu-id="b4d5b-181">Podane przykłady zostały napisane w językach C#, F# i Python, ale zestaw Quantum Development Kit obsługuje także pisanie programów klasycznych hostów w innych językach.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="b4d5b-182">[Można na przykład napisać](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net) program hosta w języku Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b4d5b-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
