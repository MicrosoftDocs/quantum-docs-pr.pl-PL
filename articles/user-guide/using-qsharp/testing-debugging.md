---
title: Testowanie i debugowanie
description: Dowiedz się, jak korzystać z testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutów do testowania i debugowania programów Quantum.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2b5276da594ba263177d435c1153f6d96e29c4e8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867917"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="e5020-103">Testowanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="e5020-103">Testing and debugging</span></span>

<span data-ttu-id="e5020-104">Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować nieprawidłowe zachowanie.</span><span class="sxs-lookup"><span data-stu-id="e5020-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="e5020-105">W tej sekcji omówiono narzędzia oferowane przez Q# program do testowania i debugowania programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="e5020-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="e5020-106">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="e5020-106">Unit Tests</span></span>

<span data-ttu-id="e5020-107">Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe*, które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="e5020-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="e5020-108">Można na przykład upewnić się, że `Square(2)` funkcja zwróci wartość, `4` ponieważ wiesz, że $2 ^ 2 = $4. *a priori*</span><span class="sxs-lookup"><span data-stu-id="e5020-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="e5020-109">Q#obsługuje tworzenie testów jednostkowych dla programów Quantum, które mogą być uruchamiane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="e5020-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="e5020-110">Tworzenie projektu testowego</span><span class="sxs-lookup"><span data-stu-id="e5020-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="e5020-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e5020-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e5020-112">Otwórz program Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="e5020-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="e5020-113">Przejdź do menu **plik** i wybierz pozycję **Nowy > projekt..**.. W prawym górnym rogu Wyszukaj `Q#` i wybierz szablon \*\* Q# projektu testowego\*\* .</span><span class="sxs-lookup"><span data-stu-id="e5020-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="e5020-114">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e5020-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e5020-115">W ulubionym wierszu polecenia Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="e5020-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="e5020-116">Nowy projekt zawiera jeden plik `Tests.qs` , który zapewnia wygodne miejsce do definiowania nowych Q# testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="e5020-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="e5020-117">Początkowo ten plik zawiera jeden przykładowy test jednostkowy, `AllocateQubit` który sprawdza, czy nowo przydzieloną qubit znajduje się w {0} stanie $ \ket $ i drukuje komunikat:</span><span class="sxs-lookup"><span data-stu-id="e5020-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="e5020-118">Każda Q# operacja lub funkcja, która przyjmuje argument typu `Unit` i Returns, `Unit` może być oznaczona jako test jednostkowy za pośrednictwem `@Test("...")` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="e5020-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="e5020-119">W poprzednim przykładzie argument dla tego atrybutu, `"QuantumSimulator"` określa obiekt docelowy, na którym przebiega testy.</span><span class="sxs-lookup"><span data-stu-id="e5020-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="e5020-120">Pojedynczy test można uruchomić na wielu celach.</span><span class="sxs-lookup"><span data-stu-id="e5020-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="e5020-121">Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` przed `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="e5020-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="e5020-122">Zapisz plik i uruchom wszystkie testy.</span><span class="sxs-lookup"><span data-stu-id="e5020-122">Save the file and run all tests.</span></span> <span data-ttu-id="e5020-123">Istnieją teraz dwa testy jednostkowe, jeden, gdzie `AllocateQubit` działa w `QuantumSimulator` programie, i jeden, gdzie działa w `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="e5020-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="e5020-124">Q#Kompilator rozpoznaje wbudowane elementy docelowe `"QuantumSimulator"` , `"ToffoliSimulator"` i `"ResourcesEstimator"` jako prawidłowe cele wykonywania dla testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="e5020-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid execution targets for unit tests.</span></span> <span data-ttu-id="e5020-125">Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania.</span><span class="sxs-lookup"><span data-stu-id="e5020-125">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="e5020-126">Uruchamianie Q# testów jednostkowych</span><span class="sxs-lookup"><span data-stu-id="e5020-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="e5020-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e5020-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e5020-128">W ramach jednorazowej konfiguracji dla poszczególnych rozwiązań przejdź do menu **test** , a następnie wybierz pozycję **Ustawienia testu > domyślna architektura procesora > x64**.</span><span class="sxs-lookup"><span data-stu-id="e5020-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="e5020-129">Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania ( `.suo` ) dla każdego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="e5020-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="e5020-130">W przypadku usunięcia tego pliku należy ponownie wybrać **procesor x64** jako architekturę procesora.</span><span class="sxs-lookup"><span data-stu-id="e5020-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="e5020-131">Skompiluj projekt, otwórz menu **test** i wybierz pozycję **Windows > Test Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e5020-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="e5020-132">**AllocateQubit** jest wyświetlana na liście testów w grupie **nie uruchomiono testów** .</span><span class="sxs-lookup"><span data-stu-id="e5020-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="e5020-133">Wybierz opcję **Uruchom wszystko** lub Uruchom ten test indywidualny.</span><span class="sxs-lookup"><span data-stu-id="e5020-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="e5020-134">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e5020-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e5020-135">Aby uruchomić testy, przejdź do folderu projektu (folder zawierający `Tests.csproj` ) i uruchom polecenie:</span><span class="sxs-lookup"><span data-stu-id="e5020-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="e5020-136">Powinny zostać wyświetlone dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="e5020-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="e5020-137">Testy jednostkowe można filtrować według ich nazwy lub celu wykonania:</span><span class="sxs-lookup"><span data-stu-id="e5020-137">Unit tests can be filtered according to their name or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="e5020-138">Wewnętrzna funkcja <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="e5020-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="e5020-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e5020-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e5020-140">Po uruchomieniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testu: stan powodzenia/niepowodzenia, czas, który upłynął, oraz link do danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="e5020-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test execution: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="e5020-141">Kliknij pozycję **dane wyjściowe** , aby otworzyć dane wyjściowe testu w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="e5020-141">Click **Output** to open the test output in a new window.</span></span>

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="e5020-143">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e5020-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e5020-144">Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli przez `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="e5020-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="e5020-145">W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.</span><span class="sxs-lookup"><span data-stu-id="e5020-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="e5020-146">Fakty i potwierdzenia</span><span class="sxs-lookup"><span data-stu-id="e5020-146">Facts and Assertions</span></span>

<span data-ttu-id="e5020-147">Ze względu na to, że funkcje w programie Q# nie mają _logicznych_ efektów ubocznych, można nie obserwować w Q# programie żadnych innych rodzajów efektów z uruchamiania funkcji, której typ danych wyjściowych jest pustą krotką `()` .</span><span class="sxs-lookup"><span data-stu-id="e5020-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="e5020-148">Oznacza to, że komputer docelowy może nie uruchamiać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących Q# kodów.</span><span class="sxs-lookup"><span data-stu-id="e5020-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="e5020-149">Takie zachowanie powoduje, że funkcje zwracają `()` (takie jak `Unit` ) użyteczne narzędzie do osadzania i debugowania w Q# programach.</span><span class="sxs-lookup"><span data-stu-id="e5020-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="e5020-150">Rozważmy prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="e5020-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="e5020-151">W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, i zgłasza wyjątek na maszynie docelowej, na której jest uruchomiony Q# program.</span><span class="sxs-lookup"><span data-stu-id="e5020-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="e5020-152">Według definicji nie można zaobserwować błędu tego rodzaju z poziomu programu Q# , ponieważ maszyna docelowa nie uruchamia już Q# kodu po osiągnięciu `fail` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="e5020-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="e5020-153">W takim przypadku, jeśli będziemy przebiegać przed wywołaniem `PositivityFact` , możemy mieć pewność, że jego dane wejściowe były dodatnie.</span><span class="sxs-lookup"><span data-stu-id="e5020-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="e5020-154">Należy pamiętać, że możemy zaimplementować takie samo zachowanie, jak `PositivityFact` Używanie [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkcji z <xref:microsoft.quantum.diagnostics> przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="e5020-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="e5020-155">Z drugiej strony, *potwierdzenia*są używane podobnie do faktów, ale mogą zależeć od stanu maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="e5020-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="e5020-156">Są one odpowiednio zdefiniowane jako operacje, natomiast fakty są definiowane jako funkcje (jak w poprzednim przykładzie).</span><span class="sxs-lookup"><span data-stu-id="e5020-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="e5020-157">Aby zrozumieć rozróżnienie, należy rozważyć następujące użycie faktu w ramach potwierdzenia:</span><span class="sxs-lookup"><span data-stu-id="e5020-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="e5020-158">W tym miejscu używamy operacji <xref:microsoft.quantum.environment.getqubitsavailabletouse> do zwrócenia liczby qubits dostępnych do użycia.</span><span class="sxs-lookup"><span data-stu-id="e5020-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="e5020-159">Ponieważ jest to zależne od stanu globalnego programu i jego środowiska wykonawczego, definicja `AssertQubitsAreAvailable` musi być operacją.</span><span class="sxs-lookup"><span data-stu-id="e5020-159">As this depends on the global state of the program and its execution environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="e5020-160">Można jednak użyć tego stanu globalnego, aby dać prostą `Bool` wartość jako dane wejściowe do `Fact` funkcji.</span><span class="sxs-lookup"><span data-stu-id="e5020-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="e5020-161">[Preludium, które](xref:microsoft.quantum.libraries.standard.prelude)tworzą na te pomysły, oferuje dwa szczególnie przydatne potwierdzenia <xref:microsoft.quantum.diagnostics.assertmeasurement> i <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> są modelowane jako operacje na `()` .</span><span class="sxs-lookup"><span data-stu-id="e5020-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="e5020-162">Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym wykonywane jest pomiary i hipotetyczny wynik.</span><span class="sxs-lookup"><span data-stu-id="e5020-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="e5020-163">Maszyny docelowe, które działają przez symulację, nie są związane [z theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestrowania, który przekazuje do takich potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="e5020-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="e5020-164">Symulator może następnie, podobnie jak `PositivityFact` poprzedniej funkcji, zatrzymać obliczenia, jeśli hipotetyczny wynik nie jest zaobserwowany w praktyce:</span><span class="sxs-lookup"><span data-stu-id="e5020-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="e5020-165">Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, `AssertMeasurement` `AssertMeasurementProbability` operacje i po prostu zwracają `()` bez żadnego skutku.</span><span class="sxs-lookup"><span data-stu-id="e5020-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="e5020-166"><xref:microsoft.quantum.diagnostics>Przestrzeń nazw udostępnia kilka funkcji `Assert` rodziny, za pomocą których można sprawdzić bardziej zaawansowane warunki.</span><span class="sxs-lookup"><span data-stu-id="e5020-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="e5020-167">Funkcje zrzutu</span><span class="sxs-lookup"><span data-stu-id="e5020-167">Dump Functions</span></span>

<span data-ttu-id="e5020-168">Aby ułatwić rozwiązywanie problemów z programami Quantum, <xref:microsoft.quantum.diagnostics> przestrzeń nazw oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="e5020-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="e5020-169">Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="e5020-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="e5020-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="e5020-170">DumpMachine</span></span>

<span data-ttu-id="e5020-171">Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="e5020-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="e5020-172">Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e5020-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="e5020-173">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e5020-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="e5020-174">Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych.</span><span class="sxs-lookup"><span data-stu-id="e5020-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="e5020-175">Szczegółowo dla pierwszego wiersza:</span><span class="sxs-lookup"><span data-stu-id="e5020-175">In detail for the first row:</span></span>

* <span data-ttu-id="e5020-176">**`∣0❭:`** Ten wiersz odnosi się do `0` stanu podstawy obliczeń</span><span class="sxs-lookup"><span data-stu-id="e5020-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="e5020-177">**`0.707107 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="e5020-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="e5020-178">**` == `**: `equal` znak oddziela obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="e5020-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="e5020-179">**`**********  `**: Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="e5020-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="e5020-180">**`[ 0.500000 ]`**: wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="e5020-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="e5020-181">**`    ---`**: Graficzna reprezentacja fazy amplitudy (patrz następujące dane wyjściowe).</span><span class="sxs-lookup"><span data-stu-id="e5020-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="e5020-182">**`[ 0.0000 rad ]`**: wartość liczbowa fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="e5020-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="e5020-183">Obie wartości i fazy są wyświetlane ze graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="e5020-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="e5020-184">Reprezentacja wielkości jest przesunięta do przodu: pokazuje pasek, tym większe prawdopodobieństwo powyższego poziomu `*` .</span><span class="sxs-lookup"><span data-stu-id="e5020-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="e5020-185">Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:</span><span class="sxs-lookup"><span data-stu-id="e5020-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="e5020-186">W poniższych przykładach przedstawiono `DumpMachine` niektóre typowe Stany:</span><span class="sxs-lookup"><span data-stu-id="e5020-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="e5020-187">Identyfikator qubit jest przypisywany w czasie wykonywania i nie musi być wyrównany do kolejności, w której został przydzielony qubit lub jej pozycji w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="e5020-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="e5020-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e5020-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="e5020-189">Identyfikator qubit można znaleźć w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:</span><span class="sxs-lookup"><span data-stu-id="e5020-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="e5020-191">qubit z indeksem `0` o `register2` identyfikatorze = `3` , qubit z indeksem `1` ma identyfikator = `2` .</span><span class="sxs-lookup"><span data-stu-id="e5020-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="e5020-192">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e5020-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="e5020-193">Identyfikator qubit można zlokalizować przy użyciu <xref:microsoft.quantum.intrinsic.message> funkcji i przekazującej zmienną qubit w komunikacie, na przykład:</span><span class="sxs-lookup"><span data-stu-id="e5020-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="e5020-194">który może generować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e5020-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="e5020-195">co oznacza, że qubit z indeksem `0` `register2` ma identyfikator = `3` , qubit z indeksem `1` ma identyfikator = `2` .</span><span class="sxs-lookup"><span data-stu-id="e5020-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="e5020-196">Ponieważ <xref:microsoft.quantum.diagnostics.dumpmachine> jest częścią <xref:microsoft.quantum.diagnostics> przestrzeni nazw, należy dodać instrukcję, `open` Aby uzyskać do niej dostęp:</span><span class="sxs-lookup"><span data-stu-id="e5020-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="e5020-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="e5020-197">DumpRegister</span></span>

<span data-ttu-id="e5020-198"><xref:microsoft.quantum.diagnostics.dumpregister>działa jak <xref:microsoft.quantum.diagnostics.dumpmachine> , z tym wyjątkiem, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.</span><span class="sxs-lookup"><span data-stu-id="e5020-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="e5020-199">Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine> , informacje generowane przez program <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="e5020-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="e5020-200">W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="e5020-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="e5020-201">Na przykład wykonaj ponownie maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[0]` wygenerowało następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e5020-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="e5020-202">i wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> metody `qubit[1]` generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e5020-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="e5020-203">Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym.</span><span class="sxs-lookup"><span data-stu-id="e5020-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="e5020-204">W takim przypadku <xref:microsoft.quantum.diagnostics.dumpregister> wyświetla następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="e5020-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="e5020-205">Poniższy przykład pokazuje, jak można używać obu <xref:microsoft.quantum.diagnostics.dumpregister> i <xref:microsoft.quantum.diagnostics.dumpmachine> w Q# kodzie:</span><span class="sxs-lookup"><span data-stu-id="e5020-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="e5020-206">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="e5020-206">Debugging</span></span>

<span data-ttu-id="e5020-207">W oparciu o `Assert` `Dump` funkcje i operacje i Q# obsługują podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), krokowe wykonywanie [kodu przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe podczas wykonywania kodu w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="e5020-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="e5020-208">Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania dostępne w języku C# dla rozszerzenia Visual Studio Code obsługiwanego przez OmniSharp i wymaga zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="e5020-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
