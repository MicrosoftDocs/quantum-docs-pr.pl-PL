---
title: 'Sposoby uruchamiania programu Q #'
description: 'Przegląd różnych sposobów uruchamiania programów Q #. Z wiersza polecenia, notesów Q # Jupyter i klasycznych programów do obsługi hostów w języku Python lub środowisku .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887738"
---
# <a name="ways-to-run-a-q-program"></a><span data-ttu-id="2cb76-104">Sposoby uruchamiania programu Q #</span><span class="sxs-lookup"><span data-stu-id="2cb76-104">Ways to run a Q# program</span></span>

<span data-ttu-id="2cb76-105">Jednym z największych zalet zestawu Quantum Development Kit jest elastyczność między platformami i środowiskami programistycznymi.</span><span class="sxs-lookup"><span data-stu-id="2cb76-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="2cb76-106">Oznacza to jednak, że nowi użytkownicy Q # mogą odmylić lub przeciążyć wiele opcji dostępnych w [przewodniku instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="2cb76-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="2cb76-107">Na tej stronie wyjaśnimy, co się dzieje w przypadku uruchomienia programu Q # i porównać różne sposoby, w których użytkownicy mogą to robić.</span><span class="sxs-lookup"><span data-stu-id="2cb76-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="2cb76-108">Podstawowa różnica polega na tym, że można uruchomić Q #:</span><span class="sxs-lookup"><span data-stu-id="2cb76-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="2cb76-109">jako aplikacja autonomiczna, gdzie Q # jest jedynym używanym językiem i program jest wywoływany bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="2cb76-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="2cb76-110">Dwie metody faktycznie należą do tej kategorii:</span><span class="sxs-lookup"><span data-stu-id="2cb76-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="2cb76-111">Interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="2cb76-111">the command line interface</span></span>
  - <span data-ttu-id="2cb76-112">Notesy programu Jupyter dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="2cb76-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="2cb76-113">za pomocą dodatkowego *programu hosta*, pisanego w języku Python lub języka .NET (np. C# lub F #), który następnie wywołuje program i może dodatkowo przetwarzać wyniki zwrócone.</span><span class="sxs-lookup"><span data-stu-id="2cb76-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="2cb76-114">Aby zapoznać się z najlepszymi procesami i ich różnicami, należy wziąć pod uwagę prosty program Q # i porównać sposoby jego wykonywania.</span><span class="sxs-lookup"><span data-stu-id="2cb76-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-q-program"></a><span data-ttu-id="2cb76-115">Basic Q # program</span><span class="sxs-lookup"><span data-stu-id="2cb76-115">Basic Q# program</span></span>

<span data-ttu-id="2cb76-116">Podstawowy program Quantum może składać się z przygotowania qubit w równej nadmiaru Stanów $ \ket {0} $ i $ \ket {1} $, mierzenia go i zwracania wyniku, który będzie losowo jednym z tych dwóch Stanów z równym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="2cb76-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="2cb76-117">W rzeczywistości ten proces jest na początku przewodnika Szybki Start dla [generatora liczb losowych](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="2cb76-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="2cb76-118">W polu Q # można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2cb76-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="2cb76-119">Jednak ten kod nie może być wykonywany przez Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="2cb76-120">W tym celu należy wykonać treść [operacji](xref:microsoft.quantum.guide.basics#q-operations-and-functions), która jest następnie wykonywana, gdy wywoływana---albo bezpośrednio lub przez inną operację.</span><span class="sxs-lookup"><span data-stu-id="2cb76-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="2cb76-121">W związku z tym można napisać operację w następującej postaci:</span><span class="sxs-lookup"><span data-stu-id="2cb76-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="2cb76-122">Zdefiniowano operację, `MeasureSuperposition` która nie pobiera danych wejściowych i zwraca wartość typu [Result](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="2cb76-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="2cb76-123">Chociaż przykłady na tej stronie składają się tylko z *operacji*q #, wszystkie koncepcje, które będziemy omawiać, odnoszą się również do *funkcji*q # i dlatego odwołują się do nich w sposób, *w jaki są*wywoływane.</span><span class="sxs-lookup"><span data-stu-id="2cb76-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="2cb76-124">Różnice między nimi są omówione w sekcji [p # podstawowe: operacje i funkcje](xref:microsoft.quantum.guide.basics#q-operations-and-functions)oraz więcej szczegółowych informacji na temat ich definiowania można znaleźć w temacie [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="2cb76-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-q-file"></a><span data-ttu-id="2cb76-125">Możliwe do przedefiniowania w pliku Q #</span><span class="sxs-lookup"><span data-stu-id="2cb76-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="2cb76-126">Wywołanie jest precyzyjnie wywoływane i uruchamiane przez Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="2cb76-127">Jednak wymaga to jeszcze kilku dodatkowych uzupełnień, które składają się na pełny `*.qs` plik Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="2cb76-128">Wszystkie typy i wartościowe elementy Q # są zdefiniowane w *przestrzeni nazw*, co zapewnia pełną nazwę, do której można się odwoływać.</span><span class="sxs-lookup"><span data-stu-id="2cb76-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="2cb76-129">Na przykład [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operacje i są dostępne w [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) przestrzeniach nazw i (część [bibliotek Q # Standard](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="2cb76-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="2cb76-130">W związku z tym zawsze można je wywoływać za pośrednictwem ich *pełnych* nazw, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale zawsze będzie to miało nieczytelny kod.</span><span class="sxs-lookup"><span data-stu-id="2cb76-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="2cb76-131">Zamiast tego `open` instrukcje umożliwiają wywoływanie z bardziej zwięzłą składnią skróconą, jak zostało to zrobione w powyższej treści operacji.</span><span class="sxs-lookup"><span data-stu-id="2cb76-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="2cb76-132">Pełny plik Q # zawierający naszą operację powinien w związku z tym zawierać definicje naszej przestrzeni nazw, otwierając przestrzenie nazw dla tych, których używa nasza operacja, a następnie naszej operacji:</span><span class="sxs-lookup"><span data-stu-id="2cb76-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="2cb76-133">W przypadku otwarcia przestrzeni nazw można również uzyskać *aliasy* , co może być przydatne w przypadku, gdy w dwóch obszarach nazw występuje konflikt nazw.</span><span class="sxs-lookup"><span data-stu-id="2cb76-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="2cb76-134">Na przykład zamiast tego możemy użyć `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` powyżej, a następnie wywołać metodę `H` `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb76-135">Jedynym wyjątkiem jest [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) przestrzeń nazw, która jest zawsze automatycznie otwierana.</span><span class="sxs-lookup"><span data-stu-id="2cb76-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="2cb76-136">W związku z tym możliwe jest, że takie wywoływanie [`Length`](xref:microsoft.quantum.core.length) może być zawsze używane bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="2cb76-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="2cb76-137">Wykonywanie na komputerach docelowych</span><span class="sxs-lookup"><span data-stu-id="2cb76-137">Execution on target machines</span></span>

<span data-ttu-id="2cb76-138">Teraz ogólny model wykonywania programu Q # zostanie wyczyszczony.</span><span class="sxs-lookup"><span data-stu-id="2cb76-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="2cb76-139">Po pierwsze, konkretnie wywoływane do wykonania ma dostęp do wszelkich innych metod i typów zdefiniowanych w tej samej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2cb76-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="2cb76-140">Uzyskują również dostęp do elementów z dowolnej [biblioteki Q #](xref:microsoft.quantum.libraries), ale muszą one być przywoływane za pośrednictwem ich pełnej nazwy lub za pomocą `open` instrukcji opisanych powyżej.</span><span class="sxs-lookup"><span data-stu-id="2cb76-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="2cb76-141">Samo wywoływanie jest wykonywane na *[maszynie docelowej](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="2cb76-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="2cb76-142">Takie maszyny docelowe mogą być rzeczywistym sprzętem Quantum lub wieloma symulatorami dostępnymi jako część QDK.</span><span class="sxs-lookup"><span data-stu-id="2cb76-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="2cb76-143">W naszym przykładzie najbardziej przydatną maszyną docelową jest wystąpienie [symulatora o pełnym stanie](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` która oblicza zachowanie programu tak, jakby było wykonywane na komputerze z systemem Quantum z nieprawidłowym hałasem.</span><span class="sxs-lookup"><span data-stu-id="2cb76-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="2cb76-144">Do tej pory opisano, co się dzieje w przypadku wykonywania określonych pytań typu Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="2cb76-145">Bez względu na to, czy Q # jest używany w aplikacji autonomicznej, czy za pomocą programu hosta, ten ogólny proces jest większy lub mniejszy---w związku z tym elastyczność QDK.</span><span class="sxs-lookup"><span data-stu-id="2cb76-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="2cb76-146">Różnice między różnymi sposobami wywołania zestawu Quantum Development Kit w ten sposób ujawniają się w *sposób* , w jaki wywołania Q # są wywoływane do wykonania i w jaki sposób są zwracane wszystkie wyniki.</span><span class="sxs-lookup"><span data-stu-id="2cb76-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="2cb76-147">Bardziej szczegółowe różnice między nimi</span><span class="sxs-lookup"><span data-stu-id="2cb76-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="2cb76-148">wskazuje, które polecenie Q # można wykonać,</span><span class="sxs-lookup"><span data-stu-id="2cb76-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="2cb76-149">jak są udostępniane potencjalną liczbę argumentów,</span><span class="sxs-lookup"><span data-stu-id="2cb76-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="2cb76-150">Określanie komputera docelowego, na którym ma zostać wykonane jego wykonywanie, oraz</span><span class="sxs-lookup"><span data-stu-id="2cb76-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="2cb76-151">sposób zwracania wyników.</span><span class="sxs-lookup"><span data-stu-id="2cb76-151">how any results are returned.</span></span>

<span data-ttu-id="2cb76-152">Najpierw omówiono, jak to zrobić za pomocą aplikacji autonomicznej Q # z wiersza polecenia, a następnie kontynuować pracę z programami hosta Python i C#.</span><span class="sxs-lookup"><span data-stu-id="2cb76-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="2cb76-153">Firma Microsoft rezerwuje autonomiczną aplikację dla notesów Q # Jupyter w ciągu ostatnich, ponieważ w przeciwieństwie do pierwszych trzech funkcja podstawowa nie Wyśrodkowuje całego lokalnego pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb76-154">Chociaż nie jest to zilustrowane w tych przykładach, jedna ze współdziałania między metodami wykonywania polega na tym, że wszystkie komunikaty, które są drukowane z wewnątrz programu Q # ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) na przykład), zazwyczaj zawsze będą drukowane do odpowiedniej konsoli.</span><span class="sxs-lookup"><span data-stu-id="2cb76-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="q-from-the-command-line"></a><span data-ttu-id="2cb76-155">Q # z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="2cb76-155">Q# from the command line</span></span>
<span data-ttu-id="2cb76-156">Jednym z najprostszych sposobów rozpoczęcia pisania p # programy jest uniknięcie przejmowania się niezależnymi plikami i drugim językiem.</span><span class="sxs-lookup"><span data-stu-id="2cb76-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="2cb76-157">Używanie Visual Studio Code lub programu Visual Studio z rozszerzeniem QDK umożliwia bezproblemowe przepływ pracy, w którym firma Microsoft jest uruchamiana z tylko jednym plikiem Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="2cb76-158">W ten sposób ostatecznie wywołamy wykonanie programu, wprowadzając</span><span class="sxs-lookup"><span data-stu-id="2cb76-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="2cb76-159">w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="2cb76-159">in the command line.</span></span>
<span data-ttu-id="2cb76-160">Najprostszym przepływem pracy jest to, że lokalizacja katalogu terminalu jest taka sama jak w przypadku pliku Q #, który można łatwo obsłużyć podczas edycji pliku Q # przy użyciu zintegrowanego terminalu w VS Code, na przykład.</span><span class="sxs-lookup"><span data-stu-id="2cb76-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="2cb76-161">Jednak [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje wiele opcji, a program może być również uruchamiany z innej lokalizacji, po prostu dostarczając `--project <PATH>` lokalizację pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-q-file"></a><span data-ttu-id="2cb76-162">Dodaj punkt wejścia do pliku Q #</span><span class="sxs-lookup"><span data-stu-id="2cb76-162">Add entry point to Q# file</span></span>

<span data-ttu-id="2cb76-163">Większość plików Q # będzie zawierać więcej niż jeden możliwy do przekroczenia, dlatego musimy poinformować kompilator o *tym, który* jest możliwy do wykonania, gdy udostępnimy `dotnet run` polecenie.</span><span class="sxs-lookup"><span data-stu-id="2cb76-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="2cb76-164">Jest to wykonywane z prostą zmianą w pliku Q #:</span><span class="sxs-lookup"><span data-stu-id="2cb76-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="2cb76-165">Dodaj wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do odwoływać.</span><span class="sxs-lookup"><span data-stu-id="2cb76-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="2cb76-166">Nasz plik z powyższych woli stać się</span><span class="sxs-lookup"><span data-stu-id="2cb76-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="2cb76-167">Teraz wywołanie `dotnet run` z wiersza polecenia prowadzi do `MeasureSuperposition` uruchomienia, a zwracana wartość jest następnie drukowana bezpośrednio do terminalu.</span><span class="sxs-lookup"><span data-stu-id="2cb76-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="2cb76-168">W związku z tym zobaczysz `One` lub `Zero` Wydrukowano.</span><span class="sxs-lookup"><span data-stu-id="2cb76-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="2cb76-169">Należy pamiętać, że nie ma znaczenia, czy masz więcej żądanych, zdefiniowanych poniżej, tylko `MeasureSuperposition` zostanie uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="2cb76-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="2cb76-170">Ponadto nie jest to problem, jeśli Twoje wywoływane dane zawierają [Komentarze dokumentacji](xref:microsoft.quantum.guide.filestructure#documentation-comments) przed jej deklaracją, `@EntryPoint()` atrybut może być po prostu umieszczony nad nimi.</span><span class="sxs-lookup"><span data-stu-id="2cb76-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="2cb76-171">Wywoływane argumenty</span><span class="sxs-lookup"><span data-stu-id="2cb76-171">Callable arguments</span></span>

<span data-ttu-id="2cb76-172">Do tej pory uważamy tylko operację, która nie pobiera danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="2cb76-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="2cb76-173">Załóżmy, że chcemy wykonać podobną operację, ale na wielu qubits---liczbę, która jest dostarczana jako argument.</span><span class="sxs-lookup"><span data-stu-id="2cb76-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="2cb76-174">Taka operacja może być zapisywana jako</span><span class="sxs-lookup"><span data-stu-id="2cb76-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="2cb76-175">gdzie zwrócona wartość jest tablicą wyników pomiaru.</span><span class="sxs-lookup"><span data-stu-id="2cb76-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="2cb76-176">Należy zauważyć, że [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) i [`ForEach`](xref:microsoft.quantum.arrays.foreach) znajdują się w [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) przestrzeniach nazw i wymaga dodatkowych `open` instrukcji dla każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="2cb76-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="2cb76-177">Jeśli przeniesiemy `@EntryPoint()` atrybut, aby poprzedzał tę nową operację (należy pamiętać, że w pliku może znajdować się tylko jeden wiersz), a próba uruchomienia go z prostu powoduje wyświetlenie `dotnet run` komunikatu o błędzie, który wskazuje, jakie dodatkowe opcje wiersza polecenia są wymagane i jak je przedstawić.</span><span class="sxs-lookup"><span data-stu-id="2cb76-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="2cb76-178">Ogólny format wiersza polecenia jest w rzeczywistości i w `dotnet run [options]` tym miejscu są dostępne argumenty.</span><span class="sxs-lookup"><span data-stu-id="2cb76-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="2cb76-179">W takim przypadku `n` Brak argumentu i pokazuje, że musimy podać opcję `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="2cb76-180">W `MeasureSuperpositionArray` związku z `n=4` tym qubits</span><span class="sxs-lookup"><span data-stu-id="2cb76-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="2cb76-181">zwraca dane wyjściowe podobne do</span><span class="sxs-lookup"><span data-stu-id="2cb76-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="2cb76-182">Ten kurs rozciąga się na wiele argumentów.</span><span class="sxs-lookup"><span data-stu-id="2cb76-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb76-183">Nazwy argumentów zdefiniowane w programie `camelCase` są nieco modyfikowane przez kompilator, który ma zostać zaakceptowany jako dane wejściowe Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="2cb76-184">Na przykład, jeśli zamiast `n` , użyto `numQubits` powyższej nazwy, to dane wejściowe byłyby dostępne w wierszu polecenia `--num-qubits 4` zamiast `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="2cb76-185">Komunikat o błędzie zawiera również inne opcje, które mogą być używane, w tym informacje o sposobie zmiany maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="2cb76-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="2cb76-186">Różne maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="2cb76-186">Different target machines</span></span>

<span data-ttu-id="2cb76-187">Ponieważ dane wyjściowe naszych operacji zostały z tego względu oczekiwane wyniki ich działania w realnej qubits, jest to oczywiste, że domyślną maszyną docelową z wiersza polecenia jest quauntum symulator, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="2cb76-188">Można jednak wydać możliwość uruchomienia na konkretnym komputerze docelowym z opcją `--simulator` (lub skrótem `-s` ).</span><span class="sxs-lookup"><span data-stu-id="2cb76-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="2cb76-189">Można na przykład uruchomić ją na [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="2cb76-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="2cb76-190">Drukowane dane wyjściowe są następnie</span><span class="sxs-lookup"><span data-stu-id="2cb76-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="2cb76-191">Aby uzyskać szczegółowe informacje na temat tego, co wskazują te metryki, zobacz [Resource szacowania: raportowane metryki](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="2cb76-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="2cb76-192">Podsumowanie wykonania wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="2cb76-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a><span data-ttu-id="2cb76-193">Opcje inne niż Q # `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="2cb76-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="2cb76-194">Jak opisano powyżej przy użyciu `--project` opcji, [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje również opcje niepowiązane z argumentami Q #, które można wywołać.</span><span class="sxs-lookup"><span data-stu-id="2cb76-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="2cb76-195">W przypadku udostępniania obu rodzajów opcji `dotnet` należy najpierw podać opcje specyficzne, po których następuje ogranicznik `--` , a następnie opcje dotyczące opcji Q.</span><span class="sxs-lookup"><span data-stu-id="2cb76-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="2cb76-196">Na przykład specifiying ścieżka wraz z liczbą qubits dla operacji powyżej zostanie wykonana za pośrednictwem `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="q-with-host-programs"></a><span data-ttu-id="2cb76-197">Q # z programami hosta</span><span class="sxs-lookup"><span data-stu-id="2cb76-197">Q# with host programs</span></span>

<span data-ttu-id="2cb76-198">Dzięki naszemu plikowi Q # alternatywą do wywołania operacji lub funkcji bezpośrednio z wiersza polecenia jest użycie *programu hosta* w innym klasycznym języku.</span><span class="sxs-lookup"><span data-stu-id="2cb76-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="2cb76-199">W szczególności można to zrobić za pomocą języka Python lub środowiska .NET, takiego jak C# lub F # (na przykład w przypadku zwięzłości w tym miejscu zostanie przedstawione szczegółowe informacje dotyczące języka C#).</span><span class="sxs-lookup"><span data-stu-id="2cb76-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="2cb76-200">Aby włączyć współdziałanie, wymagana jest nieco większa konfiguracja, ale te szczegóły znajdują się w [przewodnikach instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="2cb76-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="2cb76-201">W Nutshell sytuacja obejmuje teraz plik programu hosta (np. `*.py` lub `*.cs` ) w tej samej lokalizacji, w której znajduje się plik Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="2cb76-202">Teraz jest to program *hosta* , który jest uruchamiany i w trakcie jego wykonywania może wywoływać określone operacje Q # i funkcje z pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="2cb76-203">Rdzeń współdziałania jest oparty na kompilatorze Q #, dzięki czemu zawartość pliku Q # jest dostępna dla programu hosta, dzięki czemu mogą one być wywoływane.</span><span class="sxs-lookup"><span data-stu-id="2cb76-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="2cb76-204">Jedną z głównych zalet korzystania z programu hosta jest to, że klasyczne dane zwrócone przez program Q # można następnie przetworzyć w języku hosta.</span><span class="sxs-lookup"><span data-stu-id="2cb76-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="2cb76-205">Może to obejmować pewne zaawansowane przetwarzanie danych (np. coś, które nie może być wykonane wewnętrznie w pytaniach Q #), a następnie wywoływanie dalszych akcji Q # na podstawie tych wyników, jak również do wykreślania wyników Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="2cb76-206">Ogólny schemat jest przedstawiony tutaj i omawiamy konkretne implementacje dla języków Python i C#.</span><span class="sxs-lookup"><span data-stu-id="2cb76-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="2cb76-207">Przykład przy użyciu programu hosta języka F # można znaleźć na [Przykłady współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="2cb76-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="2cb76-208">`@EntryPoint()`Atrybut używany dla aplikacji wiersza polecenia Q # nie może być używany z programami hosta.</span><span class="sxs-lookup"><span data-stu-id="2cb76-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="2cb76-209">Jeśli jest obecny w pliku Q # wywoływanego przez hosta, zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="2cb76-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="2cb76-210">Do pracy z różnymi programami hosta nie są wymagane żadne zmiany w `*.qs` pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="2cb76-211">Następujące implementacje programu hosta działają z tym samym plikiem Q #:</span><span class="sxs-lookup"><span data-stu-id="2cb76-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="2cb76-212">Wybierz kartę odpowiadającą posiadanym językiem hosta.</span><span class="sxs-lookup"><span data-stu-id="2cb76-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="2cb76-213">Python</span><span class="sxs-lookup"><span data-stu-id="2cb76-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="2cb76-214">Program hosta języka Python jest skonstruowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="2cb76-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="2cb76-215">Zaimportuj `qsharp` moduł, który rejestruje moduł ładujący modułów pod kątem współdziałania Q.</span><span class="sxs-lookup"><span data-stu-id="2cb76-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="2cb76-216">Dzięki temu obszary nazw Q # mają być wyświetlane jako moduły języka Python, z których można "zaimportować" pytania Q.</span><span class="sxs-lookup"><span data-stu-id="2cb76-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="2cb76-217">Należy zauważyć, że nie jest to technicznie zgodne z, które są importowane, ale raczej elementy zastępcze języka Python, które umożliwiają wywoływanie tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="2cb76-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="2cb76-218">Są one zachowane jako obiekty klas języka Python, na których używamy metod do określenia maszyn docelowych do wysyłania operacji do wykonania.</span><span class="sxs-lookup"><span data-stu-id="2cb76-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="2cb76-219">Zaimportuj te pytania Q #, które zostaną bezpośrednio wywołane---w tym przypadku, `MeasureSuperposition` i `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="2cb76-220">Po `qsharp` zaimportowaniu modułu można także zaimportować możliwe do odwoływać się bezpośrednio z przestrzeni nazw biblioteki Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="2cb76-221">W przypadku każdego innego kodu w języku Python można teraz wywołać te, które są wywoływane na określonych maszynach docelowych, i przypisać zwroty do zmiennych (jeśli zwracają wartość) do dalszych użycia.</span><span class="sxs-lookup"><span data-stu-id="2cb76-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="2cb76-222">Określanie maszyn docelowych</span><span class="sxs-lookup"><span data-stu-id="2cb76-222">Specifying target machines</span></span>
<span data-ttu-id="2cb76-223">Wywołanie operacji do uruchomienia na określonej maszynie docelowej odbywa się za pośrednictwem różnych metod języka Python dla zaimportowanego obiektu.</span><span class="sxs-lookup"><span data-stu-id="2cb76-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="2cb76-224">Na przykład program `.simulate(<args>)` używa `QuantumSimulator` do uruchamiania operacji, a tym `.estimate_resources(<args>)` samym na `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="2cb76-225">Przekazywanie danych wejściowych do Q\#</span><span class="sxs-lookup"><span data-stu-id="2cb76-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="2cb76-226">Argumenty dla elementu Q # można podać w postaci argumentu słowa kluczowego, gdzie słowo kluczowe jest nazwą argumentu w definicji o wartości Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="2cb76-227">Oznacza to, że `MeasureSuperpositionArray.simulate(n=4)` jest prawidłowy, a w rezultacie zgłosi `MeasureSuperpositionArray.simulate(4)` błąd.</span><span class="sxs-lookup"><span data-stu-id="2cb76-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="2cb76-228">W związku z tym program hosta Python</span><span class="sxs-lookup"><span data-stu-id="2cb76-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="2cb76-229">wyniki są podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="2cb76-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="2cb76-230">C#</span><span class="sxs-lookup"><span data-stu-id="2cb76-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="2cb76-231">Program hosta języka C# ma wiele składników i działa bardzo blisko z niektórymi składnikami QDK, takimi jak symulatory, które są wbudowane w języku C#.</span><span class="sxs-lookup"><span data-stu-id="2cb76-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="2cb76-232">Kompilator Q # działa w tym miejscu przez wygenerowanie równoważnej nazwy przestrzeni nazw C# z przestrzeni nazw Q # w naszym pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="2cb76-233">Następnie generuje on równoważną nazwę klasy języka C# dla każdej z elementów, które są zdefiniowane w tym polu.</span><span class="sxs-lookup"><span data-stu-id="2cb76-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="2cb76-234">Najpierw udostępniamy wszelkie klasy używane w naszym programie hosta z `using` instrukcjami, które są w przybliżeniu analagous do `open` instrukcji w naszym pliku Q #:</span><span class="sxs-lookup"><span data-stu-id="2cb76-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="2cb76-235">Następnie deklarujemy naszą przestrzeń nazw języka C#, kilka innych bitów i kawałków (zobacz pełny blok kodu poniżej), a następnie wszelkie klasyczne programowanie, które chcemy (np. przetwarzanie argumentów dla zgłaszanych elementów Q #).</span><span class="sxs-lookup"><span data-stu-id="2cb76-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="2cb76-236">Ten ostatni nie jest konieczny w naszym przypadku, ale przykład takiego użycia można znaleźć w [próbce współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="2cb76-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="2cb76-237">Maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="2cb76-237">Target machines</span></span>

<span data-ttu-id="2cb76-238">Po powrocie do pytania Q należy utworzyć wystąpienie dowolnego komputera docelowego, na którym będą wykonywane nasze operacje.</span><span class="sxs-lookup"><span data-stu-id="2cb76-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="2cb76-239">Używanie innych maszyn docelowych jest tak proste jak utworzenie wystąpienia innego, chociaż proces wykonywania operacji i przetwarzania zwrotów może być nieco inny.</span><span class="sxs-lookup"><span data-stu-id="2cb76-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="2cb76-240">W przypadku usługi zwięzłości dodaliśmy do tej [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pory, a [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [poniżej](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="2cb76-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="2cb76-241">Każda Klasa języka C# wygenerowana na podstawie operacji Q # ma `Run` metodę, a pierwszy argument, który musi być wystąpieniem maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="2cb76-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="2cb76-242">Tak, aby działała `MeasureSuperposition` na `QuantumSimulator` , używamy `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="2cb76-243">Zwrócone wyniki można następnie przypisać do zmiennych w języku C#:</span><span class="sxs-lookup"><span data-stu-id="2cb76-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="2cb76-244">`Run`Metoda jest wykonywana asynchronicznie, ponieważ będzie to miało miejsce w przypadku rzeczywistego sprzętu Quantum, w związku z czym `await` słowo kluczowe blokuje dalsze wykonywanie do momentu ukończenia zadania.</span><span class="sxs-lookup"><span data-stu-id="2cb76-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="2cb76-245">Jeśli funkcja Q # nie ma żadnych funkcji Return (tj. ma zwracany typ `Unit` ), wykonanie może być nadal wykonywane w taki sam sposób, bez przypisywania go do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="2cb76-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="2cb76-246">W takim przypadku cały wiersz będzie po prostu zawierać</span><span class="sxs-lookup"><span data-stu-id="2cb76-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="2cb76-247">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2cb76-247">Arguments</span></span>

<span data-ttu-id="2cb76-248">Wszystkie argumenty dla wywoływanej wartości Q # są po prostu przekazane jako dodatkowe argumenty po maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="2cb76-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="2cb76-249">W związku z tym wyniki `MeasureSuperpositionArray` dotyczące `n=4` qubits zostałyby pobrane za pośrednictwem</span><span class="sxs-lookup"><span data-stu-id="2cb76-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="2cb76-250">Pełny program hosta języka C# może więc wyglądać jak</span><span class="sxs-lookup"><span data-stu-id="2cb76-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="2cb76-251">W lokalizacji pliku C# programu hosta można uruchomić z wiersza polecenia, wprowadzając</span><span class="sxs-lookup"><span data-stu-id="2cb76-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="2cb76-252">w takim przypadku zobaczysz dane wyjściowe zapisywane w konsoli podobnej do</span><span class="sxs-lookup"><span data-stu-id="2cb76-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="2cb76-253">Ze względu na współdziałanie kompilatora z przestrzeniami nazw możemy Alternatywnie udostępnić nasze Q #, które nie są dostępne bez `using NamespaceName;` instrukcji i po prostu dopasowując do niej tytuł przestrzeni nazw języka C#.</span><span class="sxs-lookup"><span data-stu-id="2cb76-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="2cb76-254">Oznacza to, zamieniając `namespace host` na `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="2cb76-255">Łącznie z szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="2cb76-255">Including the resources estimator</span></span>

<span data-ttu-id="2cb76-256">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Do pobrania danych wyjściowych jest wymagana nieco inna implementacja.</span><span class="sxs-lookup"><span data-stu-id="2cb76-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="2cb76-257">Po pierwsze, zamiast tworzyć wystąpienia ich jako zmiennej przy użyciu `using` instrukcji (w miarę wykonywania operacji `QuantumSimulator` ), możemy bezpośrednio utworzyć wystąpienia obiektów klasy za pośrednictwem</span><span class="sxs-lookup"><span data-stu-id="2cb76-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="2cb76-258">Zwróć uwagę, że zamiast pojedynczego symulatora docelowego, który ma być używany przez wiele operacji Q #, został utworzony wystąpienie dla każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="2cb76-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="2cb76-259">Wynika to z faktu, że obiekty są modyfikowane, gdy są używane jako maszyny docelowe, a ich wyniki można następnie pobrać później przy użyciu metody klasy `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="2cb76-260">Aby uruchomić operacje na szacowania zasobów, użyjemy</span><span class="sxs-lookup"><span data-stu-id="2cb76-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="2cb76-261">a następnie Pobierz wyniki jako wartości rozdzielane znakami tabulacji (TSV) z `estimatorSingleQ.ToTSV()` i `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="2cb76-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="2cb76-262">Tak więc pełny program hosta w języku C#, który korzysta z obu `QuantumSimulator` i `ResourcesEstimator` może przyjmować formę:</span><span class="sxs-lookup"><span data-stu-id="2cb76-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="2cb76-263">co da wynik podobny do</span><span class="sxs-lookup"><span data-stu-id="2cb76-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a><span data-ttu-id="2cb76-264">Notesy programu Jupyter dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="2cb76-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="2cb76-265">Notesy q # Jupyter używają jądra IQ #, który umożliwia definiowanie, kompilowanie i uruchamianie niemożliwych dla jednego notesu błędów Q #,---wszystkie instrukcje, notatki i inne elementy.</span><span class="sxs-lookup"><span data-stu-id="2cb76-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="2cb76-266">Oznacza to, że chociaż istnieje możliwość zaimportowania i użycia zawartości `*.qs` plików Q #, nie jest to konieczne w modelu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="2cb76-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="2cb76-267">Tutaj szczegółowo opisano sposób uruchamiania operacji Q # zdefiniowanych powyżej, ale bardziej rozległe wprowadzenie do korzystania z notesów Q # Jupyter jest dostępne na stronie [wprowadzenie do notesów q # i Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="2cb76-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="2cb76-268">Definiowanie operacji</span><span class="sxs-lookup"><span data-stu-id="2cb76-268">Defining operations</span></span>

<span data-ttu-id="2cb76-269">W programie Q # Jupyter Notebook wprowadzasz kod Q #, tak jak będziemy z przestrzeni nazw pliku Q #.</span><span class="sxs-lookup"><span data-stu-id="2cb76-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="2cb76-270">Dzięki temu możemy umożliwić dostęp do wywoływanych z [bibliotek Q # Standard](xref:microsoft.quantum.qsharplibintro) za pomocą `open` instrukcji dla odpowiednich przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2cb76-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="2cb76-271">Po uruchomieniu komórki z taką instrukcją definicje z tych przestrzeni nazw są dostępne w całym obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="2cb76-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb76-272">Elementy [Microsoft. Quantum. wewnętrzne](xref:microsoft.quantum.intrinsic) i [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (np. [`H`](xref:microsoft.quantum.intrinsic.h) i [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) są automatycznie dostępne dla operacji zdefiniowanych w komórkach w notesach Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="2cb76-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="2cb76-273">Nie jest to jednak prawdziwe w przypadku kodu pochodzącego z zewnętrznych plików Q # Source (proces pokazywany na [wprowadzenie do notesów q # i Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="2cb76-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="2cb76-274">Podobnie Definiowanie operacji wymaga tylko zapisania kodu Q # i uruchomienia komórki.</span><span class="sxs-lookup"><span data-stu-id="2cb76-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="2cb76-275">Następnie dane wyjściowe wyświetlają następnie te operacje, które następnie mogą być wywoływane z przyszłych komórek.</span><span class="sxs-lookup"><span data-stu-id="2cb76-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="2cb76-276">Maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="2cb76-276">Target machines</span></span>

<span data-ttu-id="2cb76-277">Funkcje do uruchamiania operacji na określonych komputerach docelowych są udostępniane za pośrednictwem [poleceń IQ # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="2cb76-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="2cb76-278">Na przykład program `%simulate` korzysta z programu `QuantumSimulator` i korzysta z `%estimate` `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="2cb76-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="2cb76-279">Przekazywanie danych wejściowych do funkcji i operacji</span><span class="sxs-lookup"><span data-stu-id="2cb76-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="2cb76-280">Obecnie poleceń Magic wykonywania można używać tylko z operacjami, które nie przyjmują argumentów.</span><span class="sxs-lookup"><span data-stu-id="2cb76-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="2cb76-281">Aby uruchomić `MeasureSuperpositionArray` , musimy zdefiniować operację otoki, która następnie wywołuje operację z argumentami:</span><span class="sxs-lookup"><span data-stu-id="2cb76-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="2cb76-282">Ta operacja może być używana podobnie z `%estimate` i innymi poleceniami wykonywania.</span><span class="sxs-lookup"><span data-stu-id="2cb76-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
