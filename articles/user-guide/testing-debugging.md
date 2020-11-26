---
title: Testowanie i debugowanie
description: Dowiedz się, jak korzystać z testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutów do testowania i debugowania programów Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 17a67f0a6fa7ffb9436828178acd93e1cb87a8cd
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233987"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="95499-103">Testowanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="95499-103">Testing and debugging</span></span>

<span data-ttu-id="95499-104">Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować nieprawidłowe zachowanie.</span><span class="sxs-lookup"><span data-stu-id="95499-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="95499-105">W tej sekcji omówiono narzędzia oferowane przez Q# program do testowania i debugowania programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="95499-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="95499-106">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="95499-106">Unit Tests</span></span>

<span data-ttu-id="95499-107">Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe*, które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="95499-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="95499-108">Można na przykład upewnić się, że `Square(2)` funkcja zwróci wartość, `4` ponieważ wiesz, że $2 ^ 2 = $4. *a priori*</span><span class="sxs-lookup"><span data-stu-id="95499-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="95499-109">Q# obsługuje tworzenie testów jednostkowych dla programów Quantum, które mogą być uruchamiane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="95499-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="95499-110">Tworzenie projektu testowego</span><span class="sxs-lookup"><span data-stu-id="95499-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="95499-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="95499-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="95499-112">Otwórz program Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="95499-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="95499-113">Przejdź do menu **plik** i wybierz pozycję **Nowy > projekt..**.. W prawym górnym rogu Wyszukaj `Q#` i wybierz szablon **Q# projektu testowego** .</span><span class="sxs-lookup"><span data-stu-id="95499-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="95499-114">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="95499-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="95499-115">W ulubionym wierszu polecenia Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="95499-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="95499-116">Nowy projekt zawiera jeden plik `Tests.qs` , który zapewnia wygodne miejsce do definiowania nowych Q# testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="95499-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="95499-117">Początkowo ten plik zawiera jeden przykładowy test jednostkowy, `AllocateQubit` który sprawdza, czy nowo przydzieloną qubit znajduje się w {0} stanie $ \ket $ i drukuje komunikat:</span><span class="sxs-lookup"><span data-stu-id="95499-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="95499-118">Każda Q# operacja lub funkcja, która przyjmuje argument typu `Unit` i Returns, `Unit` może być oznaczona jako test jednostkowy za pośrednictwem `@Test("...")` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="95499-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="95499-119">W poprzednim przykładzie argument dla tego atrybutu, `"QuantumSimulator"` określa obiekt docelowy, na którym przebiega testy.</span><span class="sxs-lookup"><span data-stu-id="95499-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="95499-120">Pojedynczy test można uruchomić na wielu celach.</span><span class="sxs-lookup"><span data-stu-id="95499-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="95499-121">Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` przed `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="95499-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="95499-122">Zapisz plik i uruchom wszystkie testy.</span><span class="sxs-lookup"><span data-stu-id="95499-122">Save the file and run all tests.</span></span> <span data-ttu-id="95499-123">Istnieją teraz dwa testy jednostkowe, jeden, gdzie `AllocateQubit` działa w `QuantumSimulator` programie, i jeden, gdzie działa w `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="95499-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="95499-124">Q#Kompilator rozpoznaje wbudowane elementy docelowe `"QuantumSimulator"` , `"ToffoliSimulator"` i `"ResourcesEstimator"` jako prawidłowe elementy docelowe przebiegu dla testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="95499-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="95499-125">Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="95499-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="95499-126">Uruchamianie Q# testów jednostkowych</span><span class="sxs-lookup"><span data-stu-id="95499-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="95499-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="95499-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="95499-128">W ramach jednorazowej konfiguracji dla poszczególnych rozwiązań przejdź do menu **test** , a następnie wybierz pozycję **Ustawienia testu > domyślna architektura procesora > x64**.</span><span class="sxs-lookup"><span data-stu-id="95499-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="95499-129">Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania ( `.suo` ) dla każdego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="95499-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="95499-130">W przypadku usunięcia tego pliku należy ponownie wybrać **procesor x64** jako architekturę procesora.</span><span class="sxs-lookup"><span data-stu-id="95499-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="95499-131">Skompiluj projekt, otwórz menu **test** i wybierz pozycję **Windows > Test Explorer**.</span><span class="sxs-lookup"><span data-stu-id="95499-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="95499-132">**AllocateQubit** jest wyświetlana na liście testów w grupie **nie uruchomiono testów** .</span><span class="sxs-lookup"><span data-stu-id="95499-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="95499-133">Wybierz opcję **Uruchom wszystko** lub Uruchom ten test indywidualny.</span><span class="sxs-lookup"><span data-stu-id="95499-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="95499-134">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="95499-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="95499-135">Aby uruchomić testy, przejdź do folderu projektu (folder zawierający `Tests.csproj` ) i uruchom polecenie:</span><span class="sxs-lookup"><span data-stu-id="95499-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="95499-136">Powinny zostać wyświetlone dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="95499-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="95499-137">Testy jednostkowe można filtrować według ich nazwy lub celu przebiegu:</span><span class="sxs-lookup"><span data-stu-id="95499-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="95499-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="95499-138">\*\*_</span></span>

<span data-ttu-id="95499-139">Wewnętrzna funkcja <xref:Microsoft.Quantum.Intrinsic.Message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="95499-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="95499-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="95499-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="95499-141">Po uruchomieniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o przebiegu testu: stan powodzenia/niepowodzenia, czas, który upłynął, oraz link do danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="95499-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="95499-142">Kliknij przycisk _ \*Output\*\*, aby otworzyć dane wyjściowe testu w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="95499-142">Click _ *Output*\* to open the test output in a new window.</span></span>

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="95499-144">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="95499-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="95499-145">Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli przez `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="95499-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="95499-146">W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.</span><span class="sxs-lookup"><span data-stu-id="95499-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="95499-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="95499-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="95499-148">Fakty i potwierdzenia</span><span class="sxs-lookup"><span data-stu-id="95499-148">Facts and Assertions</span></span>

<span data-ttu-id="95499-149">Ze względu na to, że funkcje w programie Q# nie mają _logicznych_ efektów ubocznych, można nie obserwować w Q# programie żadnych innych rodzajów efektów z uruchamiania funkcji, której typ danych wyjściowych jest pustą krotką `()` .</span><span class="sxs-lookup"><span data-stu-id="95499-149">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="95499-150">Oznacza to, że komputer docelowy może nie uruchamiać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących Q# kodów.</span><span class="sxs-lookup"><span data-stu-id="95499-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="95499-151">Takie zachowanie powoduje, że funkcje zwracają `()` (takie jak `Unit` ) użyteczne narzędzie do osadzania i debugowania w Q# programach.</span><span class="sxs-lookup"><span data-stu-id="95499-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="95499-152">Rozważmy prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="95499-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="95499-153">W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, i zgłasza wyjątek na maszynie docelowej, na której jest uruchomiony Q# program.</span><span class="sxs-lookup"><span data-stu-id="95499-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="95499-154">Według definicji nie można zaobserwować błędu tego rodzaju z poziomu programu Q# , ponieważ maszyna docelowa nie uruchamia już Q# kodu po osiągnięciu `fail` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="95499-154">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="95499-155">W takim przypadku, jeśli będziemy przebiegać przed wywołaniem `PositivityFact` , możemy mieć pewność, że jego dane wejściowe były dodatnie.</span><span class="sxs-lookup"><span data-stu-id="95499-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="95499-156">Należy pamiętać, że możemy zaimplementować takie samo zachowanie, jak `PositivityFact` Używanie [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) funkcji z <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="95499-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="95499-157">_Assertions \*, z drugiej strony, są używane podobnie do faktów, ale mogą być zależne od stanu maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="95499-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="95499-158">Są one odpowiednio zdefiniowane jako operacje, natomiast fakty są definiowane jako funkcje (jak w poprzednim przykładzie).</span><span class="sxs-lookup"><span data-stu-id="95499-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="95499-159">Aby zrozumieć rozróżnienie, należy rozważyć następujące użycie faktu w ramach potwierdzenia:</span><span class="sxs-lookup"><span data-stu-id="95499-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="95499-160">W tym miejscu używamy operacji <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> do zwrócenia liczby qubits dostępnych do użycia.</span><span class="sxs-lookup"><span data-stu-id="95499-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="95499-161">Ponieważ jest to zależne od stanu globalnego programu i jego środowiska uruchomieniowego, definicja `AssertQubitsAreAvailable` musi być operacją.</span><span class="sxs-lookup"><span data-stu-id="95499-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="95499-162">Można jednak użyć tego stanu globalnego, aby dać prostą `Bool` wartość jako dane wejściowe do `Fact` funkcji.</span><span class="sxs-lookup"><span data-stu-id="95499-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="95499-163">[Preludium, które](xref:microsoft.quantum.libraries.standard.prelude)tworzą na te pomysły, oferuje dwa szczególnie przydatne potwierdzenia <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> i <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> są modelowane jako operacje na `()` .</span><span class="sxs-lookup"><span data-stu-id="95499-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="95499-164">Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym wykonywane jest pomiary i hipotetyczny wynik.</span><span class="sxs-lookup"><span data-stu-id="95499-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="95499-165">Maszyny docelowe, które działają przez symulację, nie są związane [z theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestrowania, który przekazuje do takich potwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="95499-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="95499-166">Symulator może następnie, podobnie jak `PositivityFact` poprzedniej funkcji, zatrzymać obliczenia, jeśli hipotetyczny wynik nie jest zaobserwowany w praktyce:</span><span class="sxs-lookup"><span data-stu-id="95499-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

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

<span data-ttu-id="95499-167">Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, `AssertMeasurement` `AssertMeasurementProbability` operacje i po prostu zwracają `()` bez żadnego skutku.</span><span class="sxs-lookup"><span data-stu-id="95499-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="95499-168"><xref:Microsoft.Quantum.Diagnostics>Przestrzeń nazw udostępnia kilka funkcji `Assert` rodziny, za pomocą których można sprawdzić bardziej zaawansowane warunki.</span><span class="sxs-lookup"><span data-stu-id="95499-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="95499-169">Funkcje zrzutu</span><span class="sxs-lookup"><span data-stu-id="95499-169">Dump Functions</span></span>

<span data-ttu-id="95499-170">Aby ułatwić rozwiązywanie problemów z programami Quantum, <xref:Microsoft.Quantum.Diagnostics> przestrzeń nazw oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> i <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="95499-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="95499-171">Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="95499-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="95499-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="95499-172">DumpMachine</span></span>

<span data-ttu-id="95499-173">Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="95499-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="95499-174">Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ wywołujący <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generuje te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="95499-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="95499-175">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="95499-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="95499-176">Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych.</span><span class="sxs-lookup"><span data-stu-id="95499-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="95499-177">Szczegółowo dla pierwszego wiersza:</span><span class="sxs-lookup"><span data-stu-id="95499-177">In detail for the first row:</span></span>

* <span data-ttu-id="95499-178">**`∣0❭:`** Ten wiersz odnosi się do `0` stanu podstawy obliczeń</span><span class="sxs-lookup"><span data-stu-id="95499-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="95499-179">**`0.707107 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="95499-179">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="95499-180">**` == `**: `equal` znak oddziela obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="95499-180">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="95499-181">**`**********  `**: Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="95499-181">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="95499-182">**`[ 0.500000 ]`**: wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="95499-182">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="95499-183">**`    ---`**: Graficzna reprezentacja fazy amplitudy (patrz następujące dane wyjściowe).</span><span class="sxs-lookup"><span data-stu-id="95499-183">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="95499-184">**`[ 0.0000 rad ]`**: wartość liczbowa fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="95499-184">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="95499-185">Obie wartości i fazy są wyświetlane ze graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="95499-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="95499-186">Reprezentacja wielkości jest przesunięta do przodu: pokazuje pasek, tym większe prawdopodobieństwo powyższego poziomu `*` .</span><span class="sxs-lookup"><span data-stu-id="95499-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="95499-187">Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:</span><span class="sxs-lookup"><span data-stu-id="95499-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="95499-188">W poniższych przykładach przedstawiono `DumpMachine` niektóre typowe Stany:</span><span class="sxs-lookup"><span data-stu-id="95499-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="95499-189">Identyfikator qubit jest przypisywany w czasie wykonywania i nie musi być wyrównany do kolejności, w której został przydzielony qubit lub jej pozycji w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="95499-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="95499-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="95499-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="95499-191">Identyfikator qubit można znaleźć w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:</span><span class="sxs-lookup"><span data-stu-id="95499-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="95499-193">qubit z indeksem `0` o `register2` identyfikatorze = `3` , qubit z indeksem `1` ma identyfikator = `2` .</span><span class="sxs-lookup"><span data-stu-id="95499-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="95499-194">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="95499-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="95499-195">Identyfikator qubit można zlokalizować przy użyciu <xref:Microsoft.Quantum.Intrinsic.Message> funkcji i przekazującej zmienną qubit w komunikacie, na przykład:</span><span class="sxs-lookup"><span data-stu-id="95499-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="95499-196">który może generować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="95499-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="95499-197">co oznacza, że qubit z indeksem `0` `register2` ma identyfikator = `3` , qubit z indeksem `1` ma identyfikator = `2` .</span><span class="sxs-lookup"><span data-stu-id="95499-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="95499-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="95499-198">\*\*_</span></span>

<span data-ttu-id="95499-199">Ponieważ <xref:Microsoft.Quantum.Diagnostics.DumpMachine> jest częścią  <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw, należy dodać instrukcję, `open` Aby uzyskać do niej dostęp:</span><span class="sxs-lookup"><span data-stu-id="95499-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="95499-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="95499-200">DumpRegister</span></span>

<span data-ttu-id="95499-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> działa jak <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , z tym wyjątkiem, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.</span><span class="sxs-lookup"><span data-stu-id="95499-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="95499-202">Podobnie jak w przypadku <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , informacje generowane przez program <xref:Microsoft.Quantum.Diagnostics.DumpRegister> są zależne od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="95499-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="95499-203">W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="95499-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="95499-204">Na przykład wykonaj ponownie maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ wywołujący <xref:Microsoft.Quantum.Diagnostics.DumpRegister> dla `qubit[0]` wygenerowało następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="95499-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="95499-205">i wywołanie <xref:Microsoft.Quantum.Diagnostics.DumpRegister> metody `qubit[1]` generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="95499-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="95499-206">Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym.</span><span class="sxs-lookup"><span data-stu-id="95499-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="95499-207">W takim przypadku <xref:Microsoft.Quantum.Diagnostics.DumpRegister> wyświetla następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="95499-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="95499-208">Poniższy przykład pokazuje, jak można używać obu <xref:Microsoft.Quantum.Diagnostics.DumpRegister> i <xref:Microsoft.Quantum.Diagnostics.DumpMachine> w Q# kodzie:</span><span class="sxs-lookup"><span data-stu-id="95499-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="95499-209">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="95499-209">Debugging</span></span>

<span data-ttu-id="95499-210">W oparciu o `Assert` i `Dump` funkcje i operacje Q# obsługują podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokowe wykonywanie kodu przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe, gdy uruchamiasz kod w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="95499-210">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="95499-211">Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania dostępne w języku C# dla rozszerzenia Visual Studio Code obsługiwanego przez OmniSharp i wymaga zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="95499-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
