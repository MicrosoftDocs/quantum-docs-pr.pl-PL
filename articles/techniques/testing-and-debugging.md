---
title: Testowanie i debugowanie programów Q#
description: Dowiedz się, jak używać testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutu do testowania i debugowania programów kwantowych.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030586"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="3eafb-103">Testowanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="3eafb-103">Testing and Debugging</span></span>

<span data-ttu-id="3eafb-104">Podobnie jak w przypadku programowania klasycznego, ważne jest, aby móc sprawdzić, czy programy kwantowe działają zgodnie z przeznaczeniem, i być w stanie zdiagnozować program kwantowy, który jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="3eafb-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="3eafb-105">W tej sekcji omówimy narzędzia oferowane przez Q# do testowania i debugowania programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="3eafb-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="3eafb-106">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="3eafb-106">Unit Tests</span></span>

<span data-ttu-id="3eafb-107">Jednym z typowych podejść do testowania klasycznych programów jest pisanie małych programów zwanych *testami jednostkowymi,* które uruchamiają kod w bibliotece i porównuje jego dane wyjściowe z oczekiwanymi wyjściami.</span><span class="sxs-lookup"><span data-stu-id="3eafb-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="3eafb-108">Na przykład możemy chcieć `Square(2)` zapewnić, że zwraca `4`, ponieważ wiemy *a priori,* że $2^2 = 4$.</span><span class="sxs-lookup"><span data-stu-id="3eafb-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="3eafb-109">Q# obsługuje tworzenie testów jednostkowych dla programów kwantowych i które mogą być wykonywane jako testy w ramach testowania [jednostki xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="3eafb-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="3eafb-110">Tworzenie projektu testowego</span><span class="sxs-lookup"><span data-stu-id="3eafb-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="3eafb-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3eafb-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="3eafb-112">Otwórz program Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="3eafb-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="3eafb-113">Przejdź do `File` menu `New`  >  `Project...`i wybierz opcję .</span><span class="sxs-lookup"><span data-stu-id="3eafb-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="3eafb-114">W prawym górnym rogu `Q#`wyszukaj `Q# Test Project` i wybierz szablon.</span><span class="sxs-lookup"><span data-stu-id="3eafb-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="3eafb-115">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3eafb-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="3eafb-116">W ulubionym wierszu polecenia uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="3eafb-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="3eafb-117">Nowy projekt będzie miał `Tests.qs`jeden plik, który zapewnia wygodne miejsce do definiowania nowych testów jednostkowych Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="3eafb-118">Początkowo ten plik zawiera `AllocateQubit` jeden przykładowy test jednostkowy, który sprawdza,{0}czy nowo przydzielony kubit jest w stanie $\ket $ i drukuje komunikat:</span><span class="sxs-lookup"><span data-stu-id="3eafb-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="3eafb-119">Każda operacja lub funkcja Q#, `Unit` która `Unit` przyjmuje argument typu i `@Test("...")` zwraca, może być oznaczona jako test jednostkowy za pomocą atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3eafb-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="3eafb-120">Argument do tego atrybutu, `"QuantumSimulator"` powyżej, określa cel, na którym test jest wykonywany.</span><span class="sxs-lookup"><span data-stu-id="3eafb-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="3eafb-121">Pojedynczy test może być wykonany na wielu obiektów docelowych.</span><span class="sxs-lookup"><span data-stu-id="3eafb-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="3eafb-122">Na przykład dodaj atrybut `@Test("ResourcesEstimator")` `AllocateQubit`powyżej .</span><span class="sxs-lookup"><span data-stu-id="3eafb-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="3eafb-123">Zapisz plik i wykonaj wszystkie testy.</span><span class="sxs-lookup"><span data-stu-id="3eafb-123">Save the file and execute all tests.</span></span> <span data-ttu-id="3eafb-124">Teraz powinny być dwa testy jednostkowe, jeden, gdzie AllocateQubit jest wykonywany na QuantumSimulator i jeden, gdzie jest wykonywany w ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="3eafb-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="3eafb-125">Kompilator Q# rozpoznaje wbudowane obiekty docelowe "QuantumSimulator", "ToffoliSimulator" i "ResourcesEstimator" jako prawidłowe cele wykonania dla testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="3eafb-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="3eafb-126">Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania.</span><span class="sxs-lookup"><span data-stu-id="3eafb-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="3eafb-127">Uruchamianie testów jednostkowych Q#</span><span class="sxs-lookup"><span data-stu-id="3eafb-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="3eafb-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3eafb-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="3eafb-129">Jako jednorazowa konfiguracja na rozwiązanie `Test` przejdź do `Test Settings`  >  `Default Processor Architecture`  >  `X64`menu i wybierz opcję .</span><span class="sxs-lookup"><span data-stu-id="3eafb-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="3eafb-130">Domyślne ustawienie architektury procesora dla programu Visual`.suo`Studio jest przechowywane w pliku opcji rozwiązania ( ) dla każdego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="3eafb-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="3eafb-131">Jeśli usuniesz ten plik, `X64` musisz ponownie wybrać jako architekturę procesora.</span><span class="sxs-lookup"><span data-stu-id="3eafb-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="3eafb-132">Zbuduj projekt, przejdź `Test` do menu `Windows`  >  `Test Explorer`i wybierz .</span><span class="sxs-lookup"><span data-stu-id="3eafb-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="3eafb-133">`AllocateQubit`pojawi się na liście testów `Not Run Tests` w grupie.</span><span class="sxs-lookup"><span data-stu-id="3eafb-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="3eafb-134">Wybierz `Run All` lub uruchom ten indywidualny test, a powinien on przejść!</span><span class="sxs-lookup"><span data-stu-id="3eafb-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="3eafb-135">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3eafb-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="3eafb-136">Aby uruchomić testy, przejdź do folderu `Tests.csproj`projektu (folderu, który zawiera) i wykonaj polecenie:</span><span class="sxs-lookup"><span data-stu-id="3eafb-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="3eafb-137">Powinieneś uzyskać dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="3eafb-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="3eafb-138">Testy jednostkowe mogą być filtrowane zgodnie z ich nazwą i/lub celem wykonania:</span><span class="sxs-lookup"><span data-stu-id="3eafb-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="3eafb-139">Funkcja <xref:microsoft.quantum.intrinsic.message> wewnętrzna ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="3eafb-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="3eafb-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3eafb-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="3eafb-141">Po wykonaniu testu w Eksploratorze testów i kliknięciu testu pojawi się panel z informacjami o wykonaniu testu: Stan przekazany/Nieudany, czas, który upłynął i łącze "Dane wyjściowe".</span><span class="sxs-lookup"><span data-stu-id="3eafb-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="3eafb-142">Jeśli klikniesz łącze "Dane wyjściowe", dane wyjściowe testu otworzą się w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="3eafb-142">If you click the "Output" link, test output will open in a new window.</span></span>

![wyjście testowe](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="3eafb-144">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3eafb-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="3eafb-145">Stan przebiegu/niepowodzenia dla każdego testu jest `dotnet test`drukowany na konsoli przez .</span><span class="sxs-lookup"><span data-stu-id="3eafb-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="3eafb-146">W przypadku testów, które nie po awarii są również drukowane na konsoli, aby ułatwić diagnozowanie awarii.</span><span class="sxs-lookup"><span data-stu-id="3eafb-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="3eafb-147">Fakty i twierdzenia</span><span class="sxs-lookup"><span data-stu-id="3eafb-147">Facts and Assertions</span></span>

<span data-ttu-id="3eafb-148">Ponieważ funkcje w Q# nie mają _żadnych skutków_ ubocznych logiczne, wszelkie inne `()` _rodzaje_ efektów wykonywania funkcji, których typ wyjściowy jest pustą krotki nigdy nie można zaobserwować z poziomu programu Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="3eafb-149">Oznacza to, że komputer docelowy może zdecydować `()` się nie wykonywać żadnej funkcji, która zwraca z gwarancją, że to pominięcie nie zmodyfikuje zachowanie żadnego następującego kodu Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="3eafb-150">To sprawia, `()` że funkcje `Unit`zwracające (tj. ) przydatne narzędzie do osadzania potwierdzeń i debugowania logiki w programach Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="3eafb-151">Rozważmy prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="3eafb-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="3eafb-152">W tym `fail` miejscu słowo kluczowe wskazuje, że obliczenia nie powinny być kontynuowane, zgłaszając wyjątek na komputerze docelowym z uruchomionym programem Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="3eafb-153">Z definicji nie można zaobserwować błędu tego rodzaju z poziomu Q#, `fail` ponieważ po osiągnięciu instrukcji nie jest uruchamiany żaden kod Q#.</span><span class="sxs-lookup"><span data-stu-id="3eafb-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="3eafb-154">Tak więc, jeśli przejdziemy `PositivityFact`obok wezwania do , możemy być pewni, że jego wkład był pozytywny.</span><span class="sxs-lookup"><span data-stu-id="3eafb-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="3eafb-155">Należy zauważyć, że możemy `PositivityFact` zaimplementować takie samo zachowanie jak przy użyciu [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkcji z obszaru <xref:microsoft.quantum.diagnostics> nazw:</span><span class="sxs-lookup"><span data-stu-id="3eafb-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="3eafb-156">*Twierdzenia*, z drugiej strony, są używane podobnie do faktów, ale mogą być zależne od stanu maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="3eafb-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="3eafb-157">Odpowiednio, są one definiowane jako operacje, podczas gdy fakty są definiowane jako funkcje (jak powyżej).</span><span class="sxs-lookup"><span data-stu-id="3eafb-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="3eafb-158">Aby zrozumieć rozróżnienie, należy wziąć pod uwagę następujące użycie faktu w asercji:</span><span class="sxs-lookup"><span data-stu-id="3eafb-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="3eafb-159">W tym miejscu używamy <xref:microsoft.quantum.environment.getqubitsavailabletouse> operacji, aby zwrócić liczbę kubitów dostępnych do użycia.</span><span class="sxs-lookup"><span data-stu-id="3eafb-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="3eafb-160">Ponieważ to wyraźnie zależy od globalnego stanu programu i jego `AssertQubitsAreAvailable` środowiska wykonywania, nasza definicja musi być również operacją.</span><span class="sxs-lookup"><span data-stu-id="3eafb-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="3eafb-161">Jednak możemy użyć tego stanu globalnego, `Bool` aby uzyskać `Fact` prostą wartość jako dane wejściowe do funkcji.</span><span class="sxs-lookup"><span data-stu-id="3eafb-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="3eafb-162">Opierając się na tych pomysłach, [preludium](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assertprob> oferuje dwa szczególnie `()`przydatne twierdzenia, <xref:microsoft.quantum.intrinsic.assert> a oba wzorowane na operacjach na .</span><span class="sxs-lookup"><span data-stu-id="3eafb-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="3eafb-163">Twierdzenia te obejmują operatora Pauliego opisującego konkretny pomiar zainteresowania, rejestr kwantowy, na którym ma być wykonany pomiar, oraz hipotetyczny wynik.</span><span class="sxs-lookup"><span data-stu-id="3eafb-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="3eafb-164">Na maszynach docelowych, które działają za pomocą symulacji, nie jesteśmy związani [twierdzeniem o braku klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i możemy wykonywać takie pomiary bez zakłócania rejestru przekazywanego do takich twierdzeń.</span><span class="sxs-lookup"><span data-stu-id="3eafb-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="3eafb-165">Symulator może następnie, podobnie `PositivityFact` jak funkcja powyżej, przerwać obliczenia, jeśli hipotetyczny wynik nie będzie przestrzegany w praktyce:</span><span class="sxs-lookup"><span data-stu-id="3eafb-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="3eafb-166">Na fizycznym sprzęcie kwantowym, gdzie teoria o braku `Assert` klonowania uniemożliwia badanie stanu kwantowego, operacje i `AssertProb` operacje po prostu wracają `()` bez innego efektu.</span><span class="sxs-lookup"><span data-stu-id="3eafb-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="3eafb-167">Obszar <xref:microsoft.quantum.diagnostics> nazw oferuje kilka innych `Assert` funkcji rodziny, które pozwalają nam sprawdzić bardziej zaawansowane warunki.</span><span class="sxs-lookup"><span data-stu-id="3eafb-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="3eafb-168">Funkcje zrzutu</span><span class="sxs-lookup"><span data-stu-id="3eafb-168">Dump Functions</span></span>

<span data-ttu-id="3eafb-169">Aby ułatwić rozwiązywanie problemów <xref:microsoft.quantum.diagnostics> z programami kwantowymi, obszar nazw oferuje dwie funkcje, które mogą zrzucić do pliku bieżący stan komputera docelowego: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="3eafb-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="3eafb-170">Wygenerowane dane wyjściowe każdego zależy od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="3eafb-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="3eafb-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="3eafb-171">DumpMachine</span></span>

<span data-ttu-id="3eafb-172">Pełnostanowy symulator kwantowy dystrybuowany jako część Quantum Development Kit zapisuje w pliku [funkcję fali](https://en.wikipedia.org/wiki/Wave_function) całego systemu kwantowego, jako jednowymiarową tablicę liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $\ket{n}$, gdzie $\ket{n} = \ket{b_{n-1}... b_1b_0}$ dla bitów\{$ b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="3eafb-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="3eafb-173">Na przykład na komputerze z przydzielonymi tylko dwoma kubitami i w stanie kwantowym $$ \begin{align} \ket{\psi}{1}= \frac {\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ wywołanie <xref:microsoft.quantum.diagnostics.dumpmachine> generuje to dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="3eafb-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="3eafb-174">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich kubitów w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="3eafb-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="3eafb-175">W pozostałych wierszach opisano amplitudę prawdopodobieństwa pomiaru wektora stanu podstawy $\ket{n}$ zarówno w formacie kartezjańskim, jak i biegunowym.</span><span class="sxs-lookup"><span data-stu-id="3eafb-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="3eafb-176">W szczegółach dla pierwszego rzędu:</span><span class="sxs-lookup"><span data-stu-id="3eafb-176">In detail for the first row:</span></span>

* <span data-ttu-id="3eafb-177">**`∣0❭:`** ten wiersz odpowiada `0` obliczonemu stanowi podstawy</span><span class="sxs-lookup"><span data-stu-id="3eafb-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="3eafb-178">**`0.707107 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskim.</span><span class="sxs-lookup"><span data-stu-id="3eafb-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="3eafb-179">**` == `**: `equal` znak oddziela obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="3eafb-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="3eafb-180">**`**********  `**: Graficzna reprezentacja wielkości, liczba `*` jest proporcjonalna do prawdopodobieństwa pomiaru tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="3eafb-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="3eafb-181">**`[ 0.500000 ]`**: wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="3eafb-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="3eafb-182">**`    ---`**: graficzna reprezentacja fazy amplitudy (patrz poniżej).</span><span class="sxs-lookup"><span data-stu-id="3eafb-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="3eafb-183">**`[ 0.0000 rad ]`**: wartość liczbową fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="3eafb-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="3eafb-184">Zarówno wielkość, jak i faza są wyświetlane z graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="3eafb-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="3eafb-185">Reprezentacja wielkości jest prosta: pokazuje pasek `*`, im większe prawdopodobieństwo, tym większe będzie pasek.</span><span class="sxs-lookup"><span data-stu-id="3eafb-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="3eafb-186">Dla fazy pokazujemy następujące symbole reprezentujące kąt na podstawie zakresów:</span><span class="sxs-lookup"><span data-stu-id="3eafb-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="3eafb-187">Poniższe przykłady `DumpMachine` pokazują dla niektórych wspólnych stanów:</span><span class="sxs-lookup"><span data-stu-id="3eafb-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="3eafb-188">Identyfikator kubitu jest przypisywany w czasie wykonywania i nie jest koniecznie wyrównany z kolejnością, w której kubit został przydzielony lub jego położeniem w rejestrze kubitów.</span><span class="sxs-lookup"><span data-stu-id="3eafb-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="3eafb-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3eafb-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="3eafb-190">Można wymyślić identyfikator kubitu w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej kubitowej, na przykład:</span><span class="sxs-lookup"><span data-stu-id="3eafb-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![pokaż identyfikator kubitu w programie Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="3eafb-192">kubit z `0` indeksem na `register2` `3`has id= `1` , kubit`2`z indeksem ma id = .</span><span class="sxs-lookup"><span data-stu-id="3eafb-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="3eafb-193">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3eafb-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="3eafb-194">Możesz wymyślić identyfikator kubitu za <xref:microsoft.quantum.intrinsic.message> pomocą funkcji i przekazując zmienną kubitową w wiadomości, na przykład:</span><span class="sxs-lookup"><span data-stu-id="3eafb-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="3eafb-195">które mogłyby wygenerować ten wynik:</span><span class="sxs-lookup"><span data-stu-id="3eafb-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="3eafb-196">co `0` oznacza, że kubit `register2` z indeksem na ma id =`3`, kubit z indeksem `1` ma id =`2`.</span><span class="sxs-lookup"><span data-stu-id="3eafb-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="3eafb-197"><xref:microsoft.quantum.diagnostics.dumpmachine>jest częścią <xref:microsoft.quantum.diagnostics> obszaru nazw, więc aby go użyć, `open` należy dodać instrukcję:</span><span class="sxs-lookup"><span data-stu-id="3eafb-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="3eafb-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="3eafb-198">DumpRegister</span></span>

<span data-ttu-id="3eafb-199"><xref:microsoft.quantum.diagnostics.dumpregister>działa <xref:microsoft.quantum.diagnostics.dumpmachine>jak , z wyjątkiem to również wymaga tablicy kubitów, aby ograniczyć ilość informacji tylko do tych istotnych dla odpowiednich kubitów.</span><span class="sxs-lookup"><span data-stu-id="3eafb-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="3eafb-200">Podobnie <xref:microsoft.quantum.diagnostics.dumpmachine>jak w , <xref:microsoft.quantum.diagnostics.dumpregister> informacje generowane przez zależy od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="3eafb-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="3eafb-201">Dla pełnego stanu symulator kwantowy zapisuje do pliku funkcji fali do globalnej fazy sub-systemu kwantowego generowane przez <xref:microsoft.quantum.diagnostics.dumpmachine>dostarczone kubity w tym samym formacie co .</span><span class="sxs-lookup"><span data-stu-id="3eafb-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="3eafb-202">Na{1}przykład, weź ponownie maszynę z przydzielonymi tylko dwoma kubitami i w stanie kwantowym $$ \begin{align}{2}\ket{\psi} = \frac {\sqrt }{00} \ket - \frac{(1 +{2} i)} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)} `qubit[0]` {2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> generuje to dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="3eafb-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="3eafb-203">i <xref:microsoft.quantum.diagnostics.dumpregister> wzywając `qubit[1]` do generuje ten wynik:</span><span class="sxs-lookup"><span data-stu-id="3eafb-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="3eafb-204">Ogólnie rzecz biorąc stan rejestru, który jest uwikłany w inny rejestr jest stan mieszany, a nie czysty.</span><span class="sxs-lookup"><span data-stu-id="3eafb-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="3eafb-205">W takim <xref:microsoft.quantum.diagnostics.dumpregister> przypadku wysyła następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="3eafb-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="3eafb-206">Poniższy przykład pokazuje, jak <xref:microsoft.quantum.diagnostics.dumpregister> można <xref:microsoft.quantum.diagnostics.dumpmachine> używać zarówno w kodzie Q#:</span><span class="sxs-lookup"><span data-stu-id="3eafb-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="3eafb-207">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="3eafb-207">Debugging</span></span>

<span data-ttu-id="3eafb-208">Na początku `Assert` `Dump` i funkcje i operacje, Q# obsługuje podzbiór standardowych funkcji debugowania programu Visual Studio: [ustawianie punktów przerwania linii, przechodzenie](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [przez kod przy użyciu F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) i sprawdzanie wartości [zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) są możliwe podczas wykonywania kodu w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="3eafb-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="3eafb-209">Debugowanie w programie Visual Studio Code wykorzystuje możliwości debugowania udostępniane przez rozszerzenie kodu programu Visual Studio c# obsługiwane przez omnisharp i wymaga zainstalowania [najnowszej wersji.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span><span class="sxs-lookup"><span data-stu-id="3eafb-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
