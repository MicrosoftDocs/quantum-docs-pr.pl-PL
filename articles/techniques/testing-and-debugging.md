---
title: 'Testowanie i debugowanie — techniki Q # | Microsoft Docs'
description: 'Testowanie i debugowanie — techniki Q #'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: cfc71f08be0f190d9f5f4a48796e3d0ad06d6107
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820117"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="52929-103">Testowanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="52929-103">Testing and Debugging</span></span>

<span data-ttu-id="52929-104">Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować program Quantum, który jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="52929-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="52929-105">W tej sekcji omówiono narzędzia oferowane przez Q # do testowania i debugowania programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="52929-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="52929-106">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="52929-106">Unit Tests</span></span>

<span data-ttu-id="52929-107">Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="52929-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="52929-108">Na przykład firma Microsoft może chcieć upewnić się, że `Square(2)` zwraca `4`, ponieważ *wiemy, że* $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="52929-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="52929-109">Polecenie Q # obsługuje tworzenie testów jednostkowych dla programów Quantum i które mogą być wykonywane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="52929-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="52929-110">Tworzenie projektu testowego</span><span class="sxs-lookup"><span data-stu-id="52929-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="52929-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="52929-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="52929-112">Open Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="52929-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="52929-113">Przejdź do menu `File` i wybierz pozycję `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="52929-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="52929-114">W prawym górnym rogu Wyszukaj pozycję `Q#`i wybierz szablon `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="52929-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="52929-115">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="52929-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="52929-116">W ulubionym wierszu polecenia Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="52929-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="52929-117">Nowy projekt będzie miał `Tests.qs`jednego pliku, który stanowi wygodne miejsce do zdefiniowania nowych testów.</span><span class="sxs-lookup"><span data-stu-id="52929-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="52929-118">Początkowo ten plik zawiera jeden przykładowy test jednostkowy `AllocateQubit`, który sprawdza, czy nowo przydzieloną qubit znajduje się w stanie $ \ket{0}$ i drukuje komunikat:</span><span class="sxs-lookup"><span data-stu-id="52929-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="52929-119">: New: Każda operacja Q # lub funkcja, która przyjmuje argument typu `Unit` i zwraca `Unit` może być oznaczona jako test jednostkowy za pośrednictwem atrybutu `@Test("...")`.</span><span class="sxs-lookup"><span data-stu-id="52929-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="52929-120">Argument tego atrybutu, `"QuantumSimulator"` powyżej, określa obiekt docelowy, na którym wykonywany jest test.</span><span class="sxs-lookup"><span data-stu-id="52929-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="52929-121">Pojedynczy test można wykonać na wielu celach.</span><span class="sxs-lookup"><span data-stu-id="52929-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="52929-122">Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` powyżej `AllocateQubit`.</span><span class="sxs-lookup"><span data-stu-id="52929-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="52929-123">Zapisz plik i wykonaj wszystkie testy.</span><span class="sxs-lookup"><span data-stu-id="52929-123">Save the file and execute all tests.</span></span> <span data-ttu-id="52929-124">Teraz powinny być dwa testy jednostkowe, jeden, gdzie AllocateQubit jest wykonywany w QuantumSimulator i jeden, gdzie jest wykonywany w ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="52929-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="52929-125">Kompilator Q # rozpoznaje wbudowane elementy docelowe "QuantumSimulator", "ToffoliSimulator" i "ResourcesEstimator" jako prawidłowe cele wykonywania dla testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="52929-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="52929-126">Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania.</span><span class="sxs-lookup"><span data-stu-id="52929-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="52929-127">Uruchamianie testów jednostkowych Q #</span><span class="sxs-lookup"><span data-stu-id="52929-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="52929-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="52929-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="52929-129">Jako jednorazowe skonfigurowanie poszczególnych rozwiązań przejdź do menu `Test` i wybierz `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="52929-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="52929-130">Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania (`.suo`) dla każdego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="52929-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="52929-131">W przypadku usunięcia tego pliku należy ponownie wybrać `X64` jako architekturę procesora.</span><span class="sxs-lookup"><span data-stu-id="52929-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="52929-132">Skompiluj projekt, przejdź do menu `Test` i wybierz pozycję `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="52929-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="52929-133">`AllocateQubit` zostanie wyświetlona na liście testów w grupie `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="52929-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="52929-134">Wybierz `Run All` lub Uruchom ten test indywidualny, który powinien zostać przekazany!</span><span class="sxs-lookup"><span data-stu-id="52929-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="52929-135">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="52929-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="52929-136">Aby uruchomić testy, przejdź do folderu projektu (folder, który zawiera `Tests.csproj`), a następnie wykonaj polecenie:</span><span class="sxs-lookup"><span data-stu-id="52929-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="52929-137">Powinny zostać wyświetlone dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="52929-137">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="52929-138">Testy jednostkowe można filtrować według ich nazwy i/lub celu wykonania:</span><span class="sxs-lookup"><span data-stu-id="52929-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="52929-139">Funkcja wewnętrzna <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="52929-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="52929-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="52929-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="52929-141">Po wykonaniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testów: stanie zakończonych niepowodzeniem, czas, który upłynął, i link "output".</span><span class="sxs-lookup"><span data-stu-id="52929-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="52929-142">Kliknięcie linku "output" spowoduje otwarcie danych wyjściowych testu w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="52929-142">If you click the "Output" link, test output will open in a new window.</span></span>

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="52929-144">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="52929-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="52929-145">Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli programu przez `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="52929-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="52929-146">W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.</span><span class="sxs-lookup"><span data-stu-id="52929-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="assertions"></a><span data-ttu-id="52929-147">Asercje</span><span class="sxs-lookup"><span data-stu-id="52929-147">Assertions</span></span>

<span data-ttu-id="52929-148">Ponieważ funkcje w pytaniach Q # nie mają _logicznych_ efektów ubocznych, wszelkie _Inne rodzaje_ efektów wykonywania funkcji, której typem danych wyjściowych jest pusta `()` krotka, nie można nigdy zaobserwować w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="52929-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="52929-149">Oznacza to, że komputer docelowy może nie wykonywać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących kodów Q #.</span><span class="sxs-lookup"><span data-stu-id="52929-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="52929-150">Dzięki temu funkcje zwracają `()` użytecznym narzędziem do osadzania potwierdzeń i logiki debugowania do programów Q #.</span><span class="sxs-lookup"><span data-stu-id="52929-150">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="52929-151">Tę samą logikę można zastosować do implementacji zatwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="52929-151">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="52929-152">Rozważmy prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="52929-152">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="52929-153">W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, a na komputerze docelowym z uruchomionym programem Q # nie należy przechodzić.</span><span class="sxs-lookup"><span data-stu-id="52929-153">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="52929-154">Według definicji nie można zaobserwować błędu tego rodzaju z poziomu Q #, ponieważ po osiągnięciu instrukcji `fail` nie jest uruchamiany żaden dodatkowy kod Q #.</span><span class="sxs-lookup"><span data-stu-id="52929-154">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="52929-155">W takim przypadku, jeśli będziemy przełączać się do `AssertPositive`, możemy zapewnić, że jego dane wejściowe były dodatnie.</span><span class="sxs-lookup"><span data-stu-id="52929-155">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="52929-156">W oparciu o te pomysły [Preludium](xref:microsoft.quantum.libraries.standard.prelude) oferuje dwa szczególnie przydatne potwierdzenia, <xref:microsoft.quantum.intrinsic.assert> i <xref:microsoft.quantum.intrinsic.assertprob> oba modeluje jako operacje na `()`.</span><span class="sxs-lookup"><span data-stu-id="52929-156">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="52929-157">Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym ma zostać wykonane pomiary, i hipotetyczny wynik.</span><span class="sxs-lookup"><span data-stu-id="52929-157">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="52929-158">Na komputerach docelowych, które współpracują przez symulację, nie są one powiązane z [theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestracji przesłanej do takich potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="52929-158">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="52929-159">Symulator może następnie wyglądać podobnie do powyższej funkcji `AssertPositive`, przerywanie obliczeń, jeśli hipotetyczny wynik nie zostanie zaobserwowany w praktyce:</span><span class="sxs-lookup"><span data-stu-id="52929-159">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="52929-160">Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, operacje `Assert` i `AssertProb` po prostu zwracają `()` bez żadnego skutku.</span><span class="sxs-lookup"><span data-stu-id="52929-160">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="52929-161">Przestrzeń nazw <xref:microsoft.quantum.diagnostics> zawiera kilka więcej funkcji rodziny `Assert`, co pozwala nam sprawdzić bardziej zaawansowane warunki.</span><span class="sxs-lookup"><span data-stu-id="52929-161">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="52929-162">Funkcje zrzutu</span><span class="sxs-lookup"><span data-stu-id="52929-162">Dump Functions</span></span>

<span data-ttu-id="52929-163">Aby ułatwić rozwiązywanie problemów z programami Quantum, przestrzeń nazw <xref:microsoft.quantum.diagnostics> oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="52929-163">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="52929-164">Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="52929-164">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="52929-165">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="52929-165">DumpMachine</span></span>

<span data-ttu-id="52929-166">Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="52929-166">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="52929-167">Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="52929-167">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="52929-168">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="52929-168">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="52929-169">Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych.</span><span class="sxs-lookup"><span data-stu-id="52929-169">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="52929-170">Szczegółowo dla pierwszego wiersza:</span><span class="sxs-lookup"><span data-stu-id="52929-170">In detail for the first row:</span></span>

* <span data-ttu-id="52929-171">**`∣0❭:`** ten wiersz odnosi się do `0` stanu podstawy obliczeń</span><span class="sxs-lookup"><span data-stu-id="52929-171">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="52929-172">**`0.707107 +  0.000000 i`** : amplituda prawdopodobieństwa w formacie kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="52929-172">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="52929-173">**` == `** : znak `equal` oddzieli obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="52929-173">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="52929-174">**`**********  `** : graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="52929-174">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="52929-175">**`[ 0.500000 ]`** : wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="52929-175">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="52929-176">**`    ---`** : graficzna reprezentacja fazy amplitudy (patrz poniżej).</span><span class="sxs-lookup"><span data-stu-id="52929-176">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="52929-177">**`[ 0.0000 rad ]`** : wartość liczbowa fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="52929-177">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="52929-178">Obie wartości i fazy są wyświetlane ze graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="52929-178">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="52929-179">Reprezentacja wielkości jest prosta do przodu: pokazuje pasek `*`, tym większe prawdopodobieństwo powyższego poziomu paska.</span><span class="sxs-lookup"><span data-stu-id="52929-179">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="52929-180">Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:</span><span class="sxs-lookup"><span data-stu-id="52929-180">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="52929-181">W poniższych przykładach przedstawiono `DumpMachine` niektórych typowych stanów:</span><span class="sxs-lookup"><span data-stu-id="52929-181">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="52929-182">Identyfikator qubit jest przypisywany w czasie wykonywania i nie musi być wyrównany do kolejności, w której został przydzielony qubit lub jej pozycji w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="52929-182">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="52929-183">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="52929-183">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="52929-184">Identyfikator qubit można ustalić w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:</span><span class="sxs-lookup"><span data-stu-id="52929-184">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="52929-186">qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.</span><span class="sxs-lookup"><span data-stu-id="52929-186">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="52929-187">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="52929-187">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="52929-188">Identyfikator qubit można ustalić przy użyciu funkcji <xref:microsoft.quantum.intrinsic.message> i przekazywać zmienną qubit w komunikacie, na przykład:</span><span class="sxs-lookup"><span data-stu-id="52929-188">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="52929-189">który może generować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="52929-189">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="52929-190">co oznacza, że qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.</span><span class="sxs-lookup"><span data-stu-id="52929-190">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="52929-191"><xref:microsoft.quantum.diagnostics.dumpmachine> jest częścią <xref:microsoft.quantum.diagnostics> przestrzeni nazw, dlatego aby można było jej używać, należy dodać instrukcję `open`:</span><span class="sxs-lookup"><span data-stu-id="52929-191"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="52929-192">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="52929-192">DumpRegister</span></span>

<span data-ttu-id="52929-193"><xref:microsoft.quantum.diagnostics.dumpregister> działa jak <xref:microsoft.quantum.diagnostics.dumpmachine>, z tą różnicą, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.</span><span class="sxs-lookup"><span data-stu-id="52929-193"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="52929-194">Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine>, informacje generowane przez <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="52929-194">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="52929-195">W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="52929-195">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="52929-196">Na przykład należy ponownie wykonać maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}) \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[0]` generuje te dane wyjściowe :</span><span class="sxs-lookup"><span data-stu-id="52929-196">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="52929-197">i wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[1]` generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="52929-197">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="52929-198">Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym.</span><span class="sxs-lookup"><span data-stu-id="52929-198">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="52929-199">W takim przypadku <xref:microsoft.quantum.diagnostics.dumpregister> wyświetla następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="52929-199">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="52929-200">Poniższy przykład pokazuje, jak można użyć obu <xref:microsoft.quantum.diagnostics.dumpregister> i <xref:microsoft.quantum.diagnostics.dumpmachine> w kodzie Q:</span><span class="sxs-lookup"><span data-stu-id="52929-200">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="52929-201">Debugging</span><span class="sxs-lookup"><span data-stu-id="52929-201">Debugging</span></span>

<span data-ttu-id="52929-202">W oparciu o `Assert` i `Dump` funkcje i operacje, funkcja Q # obsługuje podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [Przechodzenie przez kod przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe podczas wykonywania kodu w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="52929-202">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="52929-203">Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania udostępniane przez program C# for Visual Studio Code Extension obsługiwane przez OmniSharp i wymagające zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="52929-203">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
