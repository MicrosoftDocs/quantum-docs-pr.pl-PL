---
title: 'Techniki Q # — testowanie i debugowanie | Microsoft Docs'
description: 'Techniki Q # — testowanie i debugowanie'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183492"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="bf713-103">Testowanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="bf713-103">Testing and Debugging</span></span>

<span data-ttu-id="bf713-104">Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować program Quantum, który jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="bf713-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="bf713-105">W tej sekcji omówiono narzędzia oferowane przez Q # do testowania i debugowania programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="bf713-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="bf713-106">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="bf713-106">Unit Tests</span></span>

<span data-ttu-id="bf713-107">Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="bf713-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="bf713-108">Na przykład firma Microsoft może chcieć upewnić się, że `Square(2)` zwraca `4`, ponieważ *wiemy, że* $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="bf713-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="bf713-109">Polecenie Q # obsługuje tworzenie testów jednostkowych dla programów Quantum i które mogą być wykonywane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="bf713-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="bf713-110">Tworzenie projektu testowego</span><span class="sxs-lookup"><span data-stu-id="bf713-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="bf713-111">Program Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bf713-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="bf713-112">Otwórz program Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="bf713-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="bf713-113">Przejdź do menu `File` i wybierz pozycję `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="bf713-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="bf713-114">W Eksploratorze szablonów projektu w obszarze `Installed` > `Visual C#`wybierz szablon `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="bf713-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="bf713-115">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bf713-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="bf713-116">W ulubionym wierszu polecenia Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="bf713-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="bf713-117">W obu przypadkach nowy projekt będzie miał otwarte dwa pliki.</span><span class="sxs-lookup"><span data-stu-id="bf713-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="bf713-118">Pierwszy plik, `Tests.qs`, zapewnia wygodne miejsce do definiowania nowych testów pytań typu "Q #".</span><span class="sxs-lookup"><span data-stu-id="bf713-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="bf713-119">Początkowo ten plik zawiera jeden przykładowy test jednostkowy `AllocateQubitTest`, który sprawdza, czy nowo przydzieloną qubit znajduje się w stanie $ \ket{0}$ i drukuje komunikat:</span><span class="sxs-lookup"><span data-stu-id="bf713-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="bf713-120">Wszelkie operacje Q # zgodne z typem `(Unit => Unit)` lub funkcją zgodną z `(Unit -> Unit)` można wykonać jako test jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="bf713-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="bf713-121">Drugi plik, `TestSuiteRunner.cs` zawiera metodę, która odnajduje i uruchamia testy jednostkowe Q #.</span><span class="sxs-lookup"><span data-stu-id="bf713-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="bf713-122">Jest to metoda `TestTarget` Adnotacja z atrybutem `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="bf713-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="bf713-123">Atrybut `OperationDriver` jest częścią biblioteki rozszerzeń xUnit Microsoft. Quantum. Symulacja. xUnit.</span><span class="sxs-lookup"><span data-stu-id="bf713-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="bf713-124">Struktura testowania jednostkowego wywołuje `TestTarget` metody dla każdego testu jednostki Q #, który został odnaleziony.</span><span class="sxs-lookup"><span data-stu-id="bf713-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="bf713-125">Struktura przekazuje opis testu jednostkowego do metody za pomocą argumentu `op`.</span><span class="sxs-lookup"><span data-stu-id="bf713-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="bf713-126">Następujący wiersz kodu:</span><span class="sxs-lookup"><span data-stu-id="bf713-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="bf713-127">wykonuje test jednostkowy na `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="bf713-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="bf713-128">Domyślnie mechanizm odnajdywania testów jednostkowych szuka wszystkich funkcji Q # lub operacji typu zgodnego, które spełniają następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="bf713-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="bf713-129">Znajduje się w tym samym zestawie, co metoda oznaczona adnotacją z atrybutem `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="bf713-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="bf713-130">Znajduje się w tej samej przestrzeni nazw co metoda z adnotacją `OperationDriver` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="bf713-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="bf713-131">Ma nazwę kończącą się na `Test`.</span><span class="sxs-lookup"><span data-stu-id="bf713-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="bf713-132">Zestaw, przestrzeń nazw i sufiks dla funkcji testów jednostkowych i operacji można ustawić przy użyciu opcjonalnych parametrów `OperationDriver` atrybutu:</span><span class="sxs-lookup"><span data-stu-id="bf713-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="bf713-133">parametr `AssemblyName` ustawia nazwę zestawu, który jest wyszukiwany dla testów.</span><span class="sxs-lookup"><span data-stu-id="bf713-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="bf713-134">parametr `TestNamespace` ustawia nazwę przestrzeni nazw, która jest wyszukiwana dla testów.</span><span class="sxs-lookup"><span data-stu-id="bf713-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="bf713-135">`Suffix` ustawia sufiks nazw operacji lub funkcji, które są uznawane za testy jednostkowe.</span><span class="sxs-lookup"><span data-stu-id="bf713-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="bf713-136">Ponadto opcjonalny parametr `TestCasePrefix` umożliwia ustawienie prefiksu dla nazwy przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="bf713-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="bf713-137">Prefiks przed nazwą operacji pojawi się na liście przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="bf713-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="bf713-138">Na przykład `TestCasePrefix = "QSim:"` spowoduje, że `AllocateQubitTest` pojawić się jako `QSim:AllocateQubitTest` na liście znalezionych testów.</span><span class="sxs-lookup"><span data-stu-id="bf713-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="bf713-139">Może to być przydatne do wskazania na przykład, który symulator jest używany do uruchomienia testu.</span><span class="sxs-lookup"><span data-stu-id="bf713-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="bf713-140">Uruchamianie testów jednostkowych Q #</span><span class="sxs-lookup"><span data-stu-id="bf713-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="bf713-141">Program Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bf713-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="bf713-142">Jako jednorazowe skonfigurowanie poszczególnych rozwiązań przejdź do menu `Test` i wybierz `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="bf713-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="bf713-143">Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania (`.suo`) dla każdego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="bf713-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="bf713-144">W przypadku usunięcia tego pliku należy ponownie wybrać `X64` jako architekturę procesora.</span><span class="sxs-lookup"><span data-stu-id="bf713-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="bf713-145">Skompiluj projekt, przejdź do menu `Test` i wybierz pozycję `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="bf713-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="bf713-146">`AllocateQubitTest` zostanie wyświetlona na liście testów w grupie `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="bf713-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="bf713-147">Wybierz `Run All` lub Uruchom ten test indywidualny, który powinien zostać przekazany!</span><span class="sxs-lookup"><span data-stu-id="bf713-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="bf713-148">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bf713-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="bf713-149">Aby uruchomić testy, przejdź do folderu projektu (folder, który zawiera `Tests.csproj`), a następnie wykonaj polecenie:</span><span class="sxs-lookup"><span data-stu-id="bf713-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="bf713-150">Powinny zostać wyświetlone dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="bf713-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="bf713-151">Rejestrowanie i potwierdzenia</span><span class="sxs-lookup"><span data-stu-id="bf713-151">Logging and Assertions</span></span>

<span data-ttu-id="bf713-152">Jedną z ważnych konsekwencji, że funkcje w Q # nie mają żadnych efektów ubocznych, jest to, że wszystkie efekty wykonywania funkcji, której typem danych wyjściowych jest pusta krotka `()` nie mogą być obserwowane w ramach programu Q #.</span><span class="sxs-lookup"><span data-stu-id="bf713-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="bf713-153">Oznacza to, że komputer docelowy może nie wykonywać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących kodów Q #.</span><span class="sxs-lookup"><span data-stu-id="bf713-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="bf713-154">Dzięki temu funkcje zwracają `()` użytecznym narzędziem do osadzania potwierdzeń i logiki debugowania do programów Q #.</span><span class="sxs-lookup"><span data-stu-id="bf713-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="bf713-155">Rejestrowanie</span><span class="sxs-lookup"><span data-stu-id="bf713-155">Logging</span></span>

<span data-ttu-id="bf713-156">Funkcja wewnętrzna <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="bf713-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="bf713-157">Akcja `onLog` `QuantumSimulator` może służyć do definiowania akcji wykonywanych w przypadku wywołania kodu Q # `Message`.</span><span class="sxs-lookup"><span data-stu-id="bf713-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="bf713-158">Domyślnie zarejestrowane komunikaty są drukowane w standardowym wyjściu.</span><span class="sxs-lookup"><span data-stu-id="bf713-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="bf713-159">Podczas definiowania zestawu testów jednostkowych, zarejestrowane komunikaty można skierować do danych wyjściowych testu.</span><span class="sxs-lookup"><span data-stu-id="bf713-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="bf713-160">Gdy projekt jest tworzony na podstawie szablonu projektu testowego Q #, to przekierowanie jest wstępnie skonfigurowane dla pakietu i domyślnie utworzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="bf713-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="bf713-161">Program Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bf713-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="bf713-162">Po wykonaniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testów: stanie zakończonych niepowodzeniem, czas, który upłynął, i link "output".</span><span class="sxs-lookup"><span data-stu-id="bf713-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="bf713-163">Kliknięcie linku "output" spowoduje otwarcie danych wyjściowych testu w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="bf713-163">If you click the "Output" link, test output will open in a new window.</span></span>

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="bf713-165">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bf713-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="bf713-166">Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli programu przez `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="bf713-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="bf713-167">W przypadku niepowodzeń testów dane wyjściowe zarejestrowane w wyniku wywołania `output.WriteLine(msg)` powyżej są również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.</span><span class="sxs-lookup"><span data-stu-id="bf713-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="bf713-168">Asercje</span><span class="sxs-lookup"><span data-stu-id="bf713-168">Assertions</span></span>

<span data-ttu-id="bf713-169">Tę samą logikę można zastosować do implementacji zatwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="bf713-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="bf713-170">Rozważmy prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="bf713-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="bf713-171">W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, a na komputerze docelowym z uruchomionym programem Q # nie należy przechodzić.</span><span class="sxs-lookup"><span data-stu-id="bf713-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="bf713-172">Według definicji nie można zaobserwować błędu tego rodzaju z poziomu Q #, ponieważ po osiągnięciu instrukcji `fail` nie jest uruchamiany żaden dodatkowy kod Q #.</span><span class="sxs-lookup"><span data-stu-id="bf713-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="bf713-173">W takim przypadku, jeśli będziemy przełączać się do `AssertPositive`, możemy zapewnić, że jego dane wejściowe były dodatnie.</span><span class="sxs-lookup"><span data-stu-id="bf713-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="bf713-174">W oparciu o te pomysły [Preludium](xref:microsoft.quantum.libraries.standard.prelude) oferuje dwa szczególnie przydatne potwierdzenia, <xref:microsoft.quantum.intrinsic.assert> i <xref:microsoft.quantum.intrinsic.assertprob> oba modeluje jako operacje na `()`.</span><span class="sxs-lookup"><span data-stu-id="bf713-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="bf713-175">Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym ma zostać wykonane pomiary, i hipotetyczny wynik.</span><span class="sxs-lookup"><span data-stu-id="bf713-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="bf713-176">Na komputerach docelowych, które współpracują przez symulację, nie są one powiązane z [theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestracji przesłanej do takich potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="bf713-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="bf713-177">Symulator może następnie wyglądać podobnie do powyższej funkcji `AssertPositive`, przerywanie obliczeń, jeśli hipotetyczny wynik nie zostanie zaobserwowany w praktyce:</span><span class="sxs-lookup"><span data-stu-id="bf713-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="bf713-178">Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, operacje `Assert` i `AssertProb` po prostu zwracają `()` bez żadnego skutku.</span><span class="sxs-lookup"><span data-stu-id="bf713-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="bf713-179">Przestrzeń nazw <xref:microsoft.quantum.diagnostics> zawiera kilka więcej funkcji rodziny `Assert`, co pozwala nam sprawdzić bardziej zaawansowane warunki.</span><span class="sxs-lookup"><span data-stu-id="bf713-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="bf713-180">Funkcje zrzutu</span><span class="sxs-lookup"><span data-stu-id="bf713-180">Dump Functions</span></span>

<span data-ttu-id="bf713-181">Aby ułatwić rozwiązywanie problemów z programami Quantum, przestrzeń nazw <xref:microsoft.quantum.diagnostics> oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="bf713-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="bf713-182">Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="bf713-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="bf713-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="bf713-183">DumpMachine</span></span>

<span data-ttu-id="bf713-184">Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwo pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ dla BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="bf713-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="bf713-185">Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe :</span><span class="sxs-lookup"><span data-stu-id="bf713-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="bf713-186">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="bf713-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="bf713-187">Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych.</span><span class="sxs-lookup"><span data-stu-id="bf713-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="bf713-188">Szczegółowo dla pierwszego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bf713-188">In detail for the first row:</span></span>

* <span data-ttu-id="bf713-189">**`∣0❭:`** ten wiersz odnosi się do `0` stanu podstawy obliczeń</span><span class="sxs-lookup"><span data-stu-id="bf713-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="bf713-190">**`0.707107 +  0.000000 i`** : amplituda prawdopodobieństwa w formacie kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="bf713-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="bf713-191">**` == `** : znak `equal` oddzieli obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="bf713-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="bf713-192">**`**********  `** : graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="bf713-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="bf713-193">**`[ 0.500000 ]`** : wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="bf713-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="bf713-194">**`    ---`** : graficzna reprezentacja fazy amplitudy (patrz poniżej).</span><span class="sxs-lookup"><span data-stu-id="bf713-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="bf713-195">**`[ 0.0000 rad ]`** : wartość liczbowa fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="bf713-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="bf713-196">Obie wartości i fazy są wyświetlane ze graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="bf713-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="bf713-197">Reprezentacja wielkości jest prosta do przodu: pokazuje pasek `*`, tym większe prawdopodobieństwo powyższego poziomu paska.</span><span class="sxs-lookup"><span data-stu-id="bf713-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="bf713-198">Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:</span><span class="sxs-lookup"><span data-stu-id="bf713-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="bf713-199">W poniższych przykładach przedstawiono `DumpMachine` niektórych typowych stanów:</span><span class="sxs-lookup"><span data-stu-id="bf713-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="bf713-200">Identyfikator qubit jest przypisywany w czasie wykonywania i nie musi być wyrównany do kolejności, w której został przydzielony qubit lub jej pozycji w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="bf713-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="bf713-201">Program Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bf713-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="bf713-202">Identyfikator qubit można ustalić w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:</span><span class="sxs-lookup"><span data-stu-id="bf713-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="bf713-204">qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.</span><span class="sxs-lookup"><span data-stu-id="bf713-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="bf713-205">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bf713-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="bf713-206">Identyfikator qubit można ustalić przy użyciu funkcji <xref:microsoft.quantum.intrinsic.message> i przekazywać zmienną qubit w komunikacie, na przykład:</span><span class="sxs-lookup"><span data-stu-id="bf713-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="bf713-207">który może generować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="bf713-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="bf713-208">co oznacza, że qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.</span><span class="sxs-lookup"><span data-stu-id="bf713-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="bf713-209"><xref:microsoft.quantum.diagnostics.dumpmachine> jest częścią <xref:microsoft.quantum.diagnostics> przestrzeni nazw, dlatego aby można było jej używać, należy dodać instrukcję `open`:</span><span class="sxs-lookup"><span data-stu-id="bf713-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="bf713-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="bf713-210">DumpRegister</span></span>

<span data-ttu-id="bf713-211"><xref:microsoft.quantum.diagnostics.dumpregister> działa jak <xref:microsoft.quantum.diagnostics.dumpmachine>, z tą różnicą, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.</span><span class="sxs-lookup"><span data-stu-id="bf713-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="bf713-212">Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine>, informacje generowane przez <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="bf713-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="bf713-213">W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="bf713-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="bf713-214">Na przykład należy ponownie wykonać maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ KET{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generuje te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="bf713-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="bf713-215">i wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[1]` generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="bf713-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="bf713-216">Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym.</span><span class="sxs-lookup"><span data-stu-id="bf713-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="bf713-217">W takim przypadku <xref:microsoft.quantum.diagnostics.dumpregister> wyświetla następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="bf713-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="bf713-218">Poniższy przykład pokazuje, jak można użyć obu <xref:microsoft.quantum.diagnostics.dumpregister> i <xref:microsoft.quantum.diagnostics.dumpmachine> w kodzie Q:</span><span class="sxs-lookup"><span data-stu-id="bf713-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="bf713-219">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="bf713-219">Debugging</span></span>

<span data-ttu-id="bf713-220">W oparciu o `Assert` i `Dump` funkcje i operacje, funkcja Q # obsługuje podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania linii](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokowe wykonywanie kodu przy użyciu języka F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) i [Sprawdzanie wartości zmiennych klasycznych ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)są one możliwe podczas wykonywania kodu w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="bf713-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="bf713-221">Debugowanie w Visual Studio Code nie jest jeszcze obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="bf713-221">Debugging in Visual Studio Code is not yet supported.</span></span>

