---
title: Sposoby uruchamiania Q# programu
description: Przegląd różnych sposobów uruchamiania Q# programów. Z poziomu wiersza polecenia, Q# notesów Jupyter i klasycznych programów do obsługi hostów w języku Python lub platformie .NET.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231693"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="6deba-104">Sposoby uruchamiania Q# programu</span><span class="sxs-lookup"><span data-stu-id="6deba-104">Ways to run a Q# program</span></span>

<span data-ttu-id="6deba-105">Jednym z największych zalet zestawu Quantum Development Kit jest elastyczność między platformami i środowiskami programistycznymi.</span><span class="sxs-lookup"><span data-stu-id="6deba-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="6deba-106">Oznacza to jednak, że nowi Q# Użytkownicy mogą odmylić lub przeciążyć wiele opcji dostępnych w [przewodniku instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="6deba-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="6deba-107">Na tej stronie wyjaśnimy, co Q# się dzieje, gdy program jest uruchomiony, i Porównaj różne sposoby, w których użytkownicy mogą to robić.</span><span class="sxs-lookup"><span data-stu-id="6deba-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="6deba-108">Podstawowa różnica polega na tym, że Q# można uruchomić:</span><span class="sxs-lookup"><span data-stu-id="6deba-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="6deba-109">jako aplikacja autonomiczna, w której Q# jest jedynym używanym językiem, a program jest wywoływany bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="6deba-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="6deba-110">Dwie metody faktycznie należą do tej kategorii:</span><span class="sxs-lookup"><span data-stu-id="6deba-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="6deba-111">Interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="6deba-111">the command-line interface</span></span>
  - <span data-ttu-id="6deba-112">Q# Notesy Jupyter</span><span class="sxs-lookup"><span data-stu-id="6deba-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="6deba-113">za pomocą dodatkowego *programu hosta*, pisanego w języku Python lub języka .NET (na przykład C# lub F #), który następnie wywołuje program i może dodatkowo przetwarzać wyniki zwrócone.</span><span class="sxs-lookup"><span data-stu-id="6deba-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="6deba-114">Aby zapoznać się z najlepszymi procesami i ich różnicami, należy wziąć pod uwagę prosty Q# program i porównać sposoby jego działania.</span><span class="sxs-lookup"><span data-stu-id="6deba-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="6deba-115">Q#Program Basic</span><span class="sxs-lookup"><span data-stu-id="6deba-115">Basic Q# program</span></span>

<span data-ttu-id="6deba-116">Podstawowy program Quantum może składać się z przygotowania qubit w równej nadmiaru Stanów $ \ket {0} $ i $ \ket {1} $, mierzenia go i zwracania wyniku, który będzie losowo jednym z tych dwóch Stanów z równym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="6deba-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="6deba-117">W rzeczywistości ten proces jest na początku przewodnika Szybki Start dla [generatora liczb losowych](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="6deba-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="6deba-118">W programie Q# można to wykonać za pomocą następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="6deba-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="6deba-119">Jednak ten kod nie może być uruchamiany przez Q# .</span><span class="sxs-lookup"><span data-stu-id="6deba-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="6deba-120">W tym celu należy wykonać treść [operacji](xref:microsoft.quantum.qsharp.operationsandfunctions), która jest uruchamiana, gdy wywoływana---albo bezpośrednio lub przez inną operację.</span><span class="sxs-lookup"><span data-stu-id="6deba-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="6deba-121">W związku z tym można napisać operację w następującej postaci:</span><span class="sxs-lookup"><span data-stu-id="6deba-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="6deba-122">Zdefiniowano operację, `MeasureSuperposition` która nie pobiera danych wejściowych i zwraca wartość typu [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span><span class="sxs-lookup"><span data-stu-id="6deba-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="6deba-123">Oprócz operacji, Q# umożliwia również Hermetyzowanie deterministycznych obliczeń do funkcji.</span><span class="sxs-lookup"><span data-stu-id="6deba-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="6deba-124">Oprócz zagwarantowania, że obliczenia, które działają na qubits muszą zostać hermetyzowane do operacji, a nie funkcji, istnieje niewiele różnic między operacjami i funkcją.</span><span class="sxs-lookup"><span data-stu-id="6deba-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="6deba-125">*Nazywamy* je zbiorczo.</span><span class="sxs-lookup"><span data-stu-id="6deba-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="6deba-126">Zdefiniowane w Q# pliku</span><span class="sxs-lookup"><span data-stu-id="6deba-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="6deba-127">Wywołanie jest precyzyjnie wywoływane i uruchamiane przez Q# .</span><span class="sxs-lookup"><span data-stu-id="6deba-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="6deba-128">Jednak wymaga to kilku dodatkowych uzupełnień w celu przeprowadzenia pełnego `*.qs` Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="6deba-129">Wszystkie Q# typy i elementy, które można ustalić (zarówno te, które zostały zdefiniowane, jak i wewnętrzne dla języka) są zdefiniowane w *przestrzeni nazw*, co zapewnia pełną nazwę, do której można się odwoływać.</span><span class="sxs-lookup"><span data-stu-id="6deba-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="6deba-130">Na przykład [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operacje i są dostępne w [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) przestrzeniach nazw i (części [ Q# bibliotek standardowych](xref:microsoft.quantum.libraries.standard.intro)).</span><span class="sxs-lookup"><span data-stu-id="6deba-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="6deba-131">W związku z tym zawsze można je wywoływać za pośrednictwem ich *pełnych* nazw, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale zawsze będzie to miało nieczytelny kod.</span><span class="sxs-lookup"><span data-stu-id="6deba-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="6deba-132">Zamiast tego `open` instrukcje umożliwiają wywoływanie z bardziej zwięzłą składnią skróconą, jak zostało to zrobione w powyższej treści operacji.</span><span class="sxs-lookup"><span data-stu-id="6deba-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="6deba-133">W związku z tym pełen Q# plik zawierający naszą operację będzie obejmował Definiowanie własnej przestrzeni nazw, otwierając obszary nazw dla tych, których używa nasze operacje, a następnie naszej operacji:</span><span class="sxs-lookup"><span data-stu-id="6deba-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="6deba-134">W przypadku otwarcia przestrzeni nazw można również uzyskać *aliasy* , co może być przydatne w przypadku, gdy w dwóch obszarach nazw występuje konflikt nazw.</span><span class="sxs-lookup"><span data-stu-id="6deba-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="6deba-135">Na przykład zamiast tego możemy użyć `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` powyżej, a następnie wywołać metodę `H` `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="6deba-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-136">Jedynym wyjątkiem jest [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) przestrzeń nazw, która jest zawsze automatycznie otwierana.</span><span class="sxs-lookup"><span data-stu-id="6deba-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="6deba-137">W związku z tym możliwe jest, że takie wywoływanie [`Length`](xref:Microsoft.Quantum.Core.Length) może być zawsze używane bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="6deba-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="6deba-138">Uruchomione na maszynach docelowych</span><span class="sxs-lookup"><span data-stu-id="6deba-138">Running on target machines</span></span>

<span data-ttu-id="6deba-139">Teraz ogólny model przebiegu Q# programu zostanie wyczyszczony.</span><span class="sxs-lookup"><span data-stu-id="6deba-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="6deba-140">Po pierwsze, konkretnie wywoływane do uruchomienia ma dostęp do wszelkich innych metod i typów zdefiniowanych w tej samej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="6deba-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="6deba-141">Uzyskują również dostęp do tych elementów z dowolnej [ Q# biblioteki](xref:microsoft.quantum.libraries), ale muszą one być przywoływane za pośrednictwem ich pełnej nazwy albo za pomocą `open` instrukcji opisanych powyżej.</span><span class="sxs-lookup"><span data-stu-id="6deba-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="6deba-142">Samo wywoływanie jest uruchamiane na *[maszynie docelowej](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="6deba-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="6deba-143">Takie maszyny docelowe mogą być rzeczywistym sprzętem Quantum lub wieloma symulatorami dostępnymi jako część QDK.</span><span class="sxs-lookup"><span data-stu-id="6deba-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="6deba-144">W naszym przykładzie najbardziej przydatną maszyną docelową jest wystąpienie [symulatora pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` która oblicza zachowanie programu tak, jakby było uruchamiane na komputerze z systemem Quantum bez użycia szumu.</span><span class="sxs-lookup"><span data-stu-id="6deba-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="6deba-145">Do tej pory opisano, co się dzieje, gdy Q# zostanie uruchomione określone wywoływanie.</span><span class="sxs-lookup"><span data-stu-id="6deba-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="6deba-146">Bez względu na to, czy Q# jest używany w aplikacji autonomicznej, czy za pomocą programu hosta, ten ogólny proces jest większy lub mniejszy---tym samym elastyczność QDK.</span><span class="sxs-lookup"><span data-stu-id="6deba-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="6deba-147">Różnice między sposobami wywołania zestawu Quantum Development Kit w ten sposób ujawniają się w *sposób* , w jaki Q# wywołania wywoływane do uruchomienia i w jaki sposób są zwracane wszystkie wyniki.</span><span class="sxs-lookup"><span data-stu-id="6deba-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="6deba-148">Bardziej szczegółowe różnice są następujące:</span><span class="sxs-lookup"><span data-stu-id="6deba-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="6deba-149">Wskazuje, który Q# możliwy do uruchomienia ma być uruchamiany</span><span class="sxs-lookup"><span data-stu-id="6deba-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="6deba-150">Jak są udostępniane potencjalne możliwe do odwoływać argumenty</span><span class="sxs-lookup"><span data-stu-id="6deba-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="6deba-151">Określanie komputera docelowego, na którym ma być uruchamiany</span><span class="sxs-lookup"><span data-stu-id="6deba-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="6deba-152">Jak są zwracane wyniki</span><span class="sxs-lookup"><span data-stu-id="6deba-152">How any results are returned</span></span>

<span data-ttu-id="6deba-153">Najpierw omówiono, jak to zrobić za pomocą Q# aplikacji autonomicznej z wiersza polecenia, a następnie kontynuować korzystanie z programów obsługi języka Python i C#.</span><span class="sxs-lookup"><span data-stu-id="6deba-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="6deba-154">Firma Microsoft rezerwuje autonomiczną aplikację Q# dla notesów Jupyter w ciągu ostatnich, ponieważ w przeciwieństwie do pierwszych trzech funkcja podstawowa nie Wyśrodkowuje Q# plików lokalnych.</span><span class="sxs-lookup"><span data-stu-id="6deba-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-155">Chociaż nie jest to zilustrowane w tych przykładach, jedna ze współdziałania między metodami Run polega na tym, że wszystkie komunikaty, które są drukowane z wewnątrz Q# programu ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) na przykład), zazwyczaj będą zawsze drukowane do odpowiedniej konsoli.</span><span class="sxs-lookup"><span data-stu-id="6deba-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="6deba-156">Q# z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="6deba-156">Q# from the command prompt</span></span>
<span data-ttu-id="6deba-157">Jednym z najprostszych sposobów na rozpoczęcie pisania Q# programów jest uniknięcie przejmowania informacji o osobnych plikach i drugim języku.</span><span class="sxs-lookup"><span data-stu-id="6deba-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="6deba-158">Używanie Visual Studio Code lub Visual Studio z rozszerzeniem QDK umożliwia bezproblemowe przepływ pracy, w którym uruchamiamy wywoływany Q# z tylko jednego Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="6deba-159">W ten sposób ostatecznie uruchomimy program, wprowadzając</span><span class="sxs-lookup"><span data-stu-id="6deba-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="6deba-160">w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="6deba-160">at the command prompt.</span></span>
<span data-ttu-id="6deba-161">Najprostszym przepływem pracy jest to, że lokalizacja katalogu terminalu jest taka sama jak w przypadku Q# pliku, który można łatwo obsługiwać podczas Q# edycji plików przy użyciu zintegrowanego terminalu w vs Code, na przykład.</span><span class="sxs-lookup"><span data-stu-id="6deba-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="6deba-162">Jednak [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje wiele opcji, a program może być również uruchamiany z innej lokalizacji, po prostu dostarczając `--project <PATH>` lokalizację Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="6deba-163">Dodaj punkt wejścia do Q# pliku</span><span class="sxs-lookup"><span data-stu-id="6deba-163">Add entry point to Q# file</span></span>

<span data-ttu-id="6deba-164">Większość Q# plików będzie zawierać więcej niż jeden możliwy do oddzwonienia, więc w naturalny sposób musimy poinformować kompilator o *tym, który* jest możliwy do uruchomienia, gdy udostępnimy `dotnet run` polecenie.</span><span class="sxs-lookup"><span data-stu-id="6deba-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="6deba-165">Jest to wykonywane z prostą zmianą dla Q# samego pliku:</span><span class="sxs-lookup"><span data-stu-id="6deba-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="6deba-166">Dodaj wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do odwoływać.</span><span class="sxs-lookup"><span data-stu-id="6deba-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="6deba-167">Nasz plik z powyższych woli stać się</span><span class="sxs-lookup"><span data-stu-id="6deba-167">Our file from above would therefore become</span></span>
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

<span data-ttu-id="6deba-168">Teraz wywołanie `dotnet run` z wiersza polecenia prowadzi do `MeasureSuperposition` uruchomienia, a zwracana wartość jest następnie drukowana bezpośrednio do terminalu.</span><span class="sxs-lookup"><span data-stu-id="6deba-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="6deba-169">W związku z tym zobaczysz `One` lub `Zero` Wydrukowano.</span><span class="sxs-lookup"><span data-stu-id="6deba-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="6deba-170">Należy pamiętać, że nie ma znaczenia, czy masz więcej żądanych, zdefiniowanych poniżej, tylko `MeasureSuperposition` zostanie uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="6deba-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="6deba-171">Ponadto nie jest to problem, jeśli Twoje wywoływane dane zawierają [Komentarze dokumentacji](xref:microsoft.quantum.qsharp.comments#documentation-comments) przed jej deklaracją, `@EntryPoint()` atrybut może być po prostu umieszczony nad nimi.</span><span class="sxs-lookup"><span data-stu-id="6deba-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="6deba-172">Wywoływane argumenty</span><span class="sxs-lookup"><span data-stu-id="6deba-172">Callable arguments</span></span>

<span data-ttu-id="6deba-173">Do tej pory uważamy tylko operację, która nie pobiera danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="6deba-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="6deba-174">Załóżmy, że chcemy wykonać podobną operację, ale na wielu qubits---liczbę, która jest dostarczana jako argument.</span><span class="sxs-lookup"><span data-stu-id="6deba-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="6deba-175">Taka operacja może być zapisywana jako</span><span class="sxs-lookup"><span data-stu-id="6deba-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="6deba-176">gdzie zwrócona wartość jest tablicą wyników pomiaru.</span><span class="sxs-lookup"><span data-stu-id="6deba-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="6deba-177">Należy zauważyć, że [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) i [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) znajdują się w [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) przestrzeniach nazw i wymaga dodatkowych `open` instrukcji dla każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="6deba-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="6deba-178">Jeśli przeniesiemy `@EntryPoint()` atrybut, aby poprzedzał tę nową operację (należy pamiętać, że w pliku może znajdować się tylko jeden wiersz), a próba uruchomienia go z prostu `dotnet run` powoduje wyświetlenie komunikatu o błędzie, który wskazuje, jakie dodatkowe opcje wiersza polecenia są wymagane i jak je przedstawić.</span><span class="sxs-lookup"><span data-stu-id="6deba-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="6deba-179">Ogólny format wiersza polecenia jest w rzeczywistości i w `dotnet run [options]` tym miejscu są dostępne argumenty.</span><span class="sxs-lookup"><span data-stu-id="6deba-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="6deba-180">W takim przypadku `n` Brak argumentu i pokazuje, że musimy podać opcję `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="6deba-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="6deba-181">W `MeasureSuperpositionArray` związku z `n=4` tym qubits</span><span class="sxs-lookup"><span data-stu-id="6deba-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="6deba-182">zwraca dane wyjściowe podobne do</span><span class="sxs-lookup"><span data-stu-id="6deba-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="6deba-183">Ten kurs rozciąga się na wiele argumentów.</span><span class="sxs-lookup"><span data-stu-id="6deba-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-184">Nazwy argumentów zdefiniowane w programie `camelCase` są nieco modyfikowane przez kompilator, który ma zostać zaakceptowany jako Q# dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="6deba-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="6deba-185">Na przykład, jeśli zamiast `n` , użyto `numQubits` powyższej nazwy, to dane wejściowe byłyby dostępne w wierszu polecenia `--num-qubits 4` zamiast `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="6deba-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="6deba-186">Komunikat o błędzie zawiera również inne opcje, które mogą być używane, w tym informacje o sposobie zmiany maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="6deba-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="6deba-187">Różne maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="6deba-187">Different target machines</span></span>

<span data-ttu-id="6deba-188">Ponieważ dane wyjściowe naszych operacji zostały z tego względu oczekiwane wyniki ich działania w realnej qubits, jest to oczywiste, że domyślną maszyną docelową z wiersza polecenia jest symulator Quantum dla całego stanu `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="6deba-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="6deba-189">Można jednak wydać możliwość uruchomienia na konkretnym komputerze docelowym z opcją `--simulator` (lub skrótem `-s` ).</span><span class="sxs-lookup"><span data-stu-id="6deba-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="6deba-190">Można na przykład uruchomić ją na [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="6deba-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="6deba-191">Drukowane dane wyjściowe są następnie</span><span class="sxs-lookup"><span data-stu-id="6deba-191">The printed output is then</span></span>

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

<span data-ttu-id="6deba-192">Aby uzyskać szczegółowe informacje na temat tego, co wskazują te metryki, zobacz [Resource szacowania: raportowane metryki](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="6deba-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="6deba-193">Podsumowanie uruchamiania wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="6deba-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="6deba-194">Opcje inne niż Q# `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="6deba-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="6deba-195">Jak opisano powyżej przy użyciu `--project` opcji, [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje również opcje niezwiązane z wywoływanymi Q# argumentami.</span><span class="sxs-lookup"><span data-stu-id="6deba-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="6deba-196">W przypadku udostępniania obu rodzajów opcji `dotnet` należy najpierw podać opcje specyficzne, po których następuje ogranicznik `--` , a następnie Q# Opcje specyficzne dla programu.</span><span class="sxs-lookup"><span data-stu-id="6deba-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="6deba-197">Na przykład określenie ścieżki wraz z liczbą qubits dla operacji powyżej zostanie uruchomione za pośrednictwem `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="6deba-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="6deba-198">Q# z programami hosta</span><span class="sxs-lookup"><span data-stu-id="6deba-198">Q# with host programs</span></span>

<span data-ttu-id="6deba-199">W przypadku naszego Q# pliku, alternatywą do wywołania operacji lub funkcji bezpośrednio z wiersza polecenia jest użycie *programu hosta* w innym klasycznym języku.</span><span class="sxs-lookup"><span data-stu-id="6deba-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="6deba-200">W szczególności można to zrobić za pomocą języka Python lub środowiska .NET, takiego jak C# lub F # (na przykład w przypadku zwięzłości w tym miejscu zostanie przedstawione szczegółowe informacje dotyczące języka C#).</span><span class="sxs-lookup"><span data-stu-id="6deba-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="6deba-201">Aby włączyć współdziałanie, wymagana jest nieco większa konfiguracja, ale te szczegóły znajdują się w [przewodnikach instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="6deba-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="6deba-202">W Nutshell sytuacja zawiera teraz plik programu hosta (na przykład `*.py` lub `*.cs` ) w tej samej lokalizacji, w której znajduje się Q# plik.</span><span class="sxs-lookup"><span data-stu-id="6deba-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="6deba-203">Teraz jest to program *hosta* , który jest uruchamiany, a gdy jest uruchomiony, może wywołać określone Q# operacje i funkcje z Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="6deba-204">Rdzeń współdziałania jest oparty na kompilatorze, dzięki czemu Q# zawartość pliku jest Q# dostępna dla programu hosta, dzięki czemu mogą one być wywoływane.</span><span class="sxs-lookup"><span data-stu-id="6deba-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="6deba-205">Jedną z głównych zalet korzystania z programu hosta jest to, że klasyczne dane zwrócone przez Q# program można następnie przetworzyć w języku hosta.</span><span class="sxs-lookup"><span data-stu-id="6deba-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="6deba-206">Może to obejmować pewne zaawansowane przetwarzanie danych (np. coś, które nie może być wykonane wewnętrznie w programie Q# ), a następnie wywoływanie dalszych Q# akcji na podstawie tych wyników, jak również do wykreślania Q# wyników.</span><span class="sxs-lookup"><span data-stu-id="6deba-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="6deba-207">Ogólny schemat jest przedstawiony tutaj i omawiamy konkretne implementacje dla języków Python i C#.</span><span class="sxs-lookup"><span data-stu-id="6deba-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="6deba-208">Przykład przy użyciu programu hosta języka F # można znaleźć na [Przykłady współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="6deba-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="6deba-209">`@EntryPoint()`Atrybut używany dla Q# aplikacji nie może być używany z programami hosta.</span><span class="sxs-lookup"><span data-stu-id="6deba-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="6deba-210">Jeśli jest obecny w Q# pliku wywoływanym przez hosta, zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="6deba-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="6deba-211">Do pracy z różnymi programami hosta nie są wymagane żadne zmiany do `*.qs` Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="6deba-212">Następujące implementacje programu hosta działają z tym samym Q# plikiem:</span><span class="sxs-lookup"><span data-stu-id="6deba-212">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="6deba-213">Wybierz kartę odpowiadającą posiadanym językiem hosta.</span><span class="sxs-lookup"><span data-stu-id="6deba-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="6deba-214">Python</span><span class="sxs-lookup"><span data-stu-id="6deba-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="6deba-215">Program hosta języka Python jest skonstruowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6deba-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="6deba-216">Zaimportuj `qsharp` moduł, który rejestruje moduł ładujący modułu pod kątem Q# współdziałania.</span><span class="sxs-lookup"><span data-stu-id="6deba-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="6deba-217">Dzięki temu Q# przestrzenie nazw mogą być wyświetlane jako moduły języka Python, z których można "zaimportować" Q# .</span><span class="sxs-lookup"><span data-stu-id="6deba-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="6deba-218">Należy zauważyć, że nie jest to technicznie możliwe do Q# zaimportowania, ale raczej elementy zastępcze języka Python, które umożliwiają wywoływanie.</span><span class="sxs-lookup"><span data-stu-id="6deba-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="6deba-219">Działają one jako obiekty klas języka Python.</span><span class="sxs-lookup"><span data-stu-id="6deba-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="6deba-220">Używamy metod dla tych obiektów, aby określić maszyny docelowe, do których wysyłamy operację podczas uruchamiania programu.</span><span class="sxs-lookup"><span data-stu-id="6deba-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="6deba-221">Zaimportuj te Q# , które zostały wywołane bezpośrednio---w tym przypadku, `MeasureSuperposition` i `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="6deba-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="6deba-222">Po `qsharp` zaimportowaniu modułu można także zaimportować możliwe do odwoływać się bezpośrednio z Q# przestrzeni nazw biblioteki.</span><span class="sxs-lookup"><span data-stu-id="6deba-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="6deba-223">W przypadku każdego innego kodu w języku Python można teraz wywołać te, które są wywoływane na określonych maszynach docelowych, i przypisać zwroty do zmiennych (jeśli zwracają wartość) do dalszych użycia.</span><span class="sxs-lookup"><span data-stu-id="6deba-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="6deba-224">Określanie maszyn docelowych</span><span class="sxs-lookup"><span data-stu-id="6deba-224">Specifying target machines</span></span>
<span data-ttu-id="6deba-225">Wywołanie operacji do uruchomienia na określonej maszynie docelowej odbywa się za pośrednictwem różnych metod języka Python dla zaimportowanego obiektu.</span><span class="sxs-lookup"><span data-stu-id="6deba-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="6deba-226">Na przykład program `.simulate(<args>)` używa `QuantumSimulator` do uruchamiania operacji, a tym `.estimate_resources(<args>)` samym na `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="6deba-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="6deba-227">Przekazywanie danych wejściowych do Q\#</span><span class="sxs-lookup"><span data-stu-id="6deba-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="6deba-228">Argumenty dla wywoływanej wartości Q# powinny być podane w postaci argumentu słowa kluczowego, gdzie słowo kluczowe jest nazwą argumentu w definicji, którą można Q# wywołać.</span><span class="sxs-lookup"><span data-stu-id="6deba-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="6deba-229">Oznacza to, że `MeasureSuperpositionArray.simulate(n=4)` jest prawidłowy, a w rezultacie zgłosi `MeasureSuperpositionArray.simulate(4)` błąd.</span><span class="sxs-lookup"><span data-stu-id="6deba-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="6deba-230">W związku z tym program hosta Python</span><span class="sxs-lookup"><span data-stu-id="6deba-230">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="6deba-231">wyniki są podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="6deba-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="6deba-232">Używanie Q# kodu z innych projektów lub pakietów</span><span class="sxs-lookup"><span data-stu-id="6deba-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="6deba-233">Domyślnie `import qsharp` polecenie ładuje wszystkie `.qs` pliki w bieżącym folderze i sprawia, że ich Q# operacje i funkcje są dostępne do użycia w skrypcie języka Python.</span><span class="sxs-lookup"><span data-stu-id="6deba-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="6deba-234">Aby załadować Q# kod z innego folderu, można użyć [ `qsharp.projects` interfejsu API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) w celu dodania odwołania do `.csproj` pliku dla Q# projektu (czyli projektu, do którego się odwołuje `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="6deba-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="6deba-235">To polecenie spowoduje skompilowanie wszystkich `.qs` plików w folderze zawierającym `.csproj` i jego podfolderach.</span><span class="sxs-lookup"><span data-stu-id="6deba-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="6deba-236">Spowoduje również cykliczne załadowanie wszelkich pakietów, do których odwołuje się `PackageReference` lub Q# projekty, do których odwołuje się `ProjectReference` ten `.csproj` plik.</span><span class="sxs-lookup"><span data-stu-id="6deba-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="6deba-237">Na przykład poniższy kod języka Python importuje projekt zewnętrzny, odwołujący się do jego ścieżki względnej do bieżącego folderu i wywołuje jedną z jej Q# operacji:</span><span class="sxs-lookup"><span data-stu-id="6deba-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="6deba-238">Wyniki są podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="6deba-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="6deba-239">Aby załadować pakiety zewnętrzne zawierające Q# kod, użyj [ `qsharp.packages` interfejsu API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="6deba-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="6deba-240">Jeśli Q# kod w bieżącym folderze zależy od zewnętrznych projektów lub pakietów, mogą pojawić `import qsharp` się błędy, ponieważ zależności nie zostały jeszcze załadowane.</span><span class="sxs-lookup"><span data-stu-id="6deba-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="6deba-241">Aby załadować wymagane pakiety zewnętrzne lub Q# projekty podczas wykonywania `import qsharp` polecenia, upewnij się, że folder z skryptem języka Python zawiera `.csproj` plik, którego dotyczy odwołanie `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="6deba-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="6deba-242">W tym `.csproj` celu należy dodać właściwość `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="6deba-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="6deba-243">Spowoduje to wymuszenie Q# cyklicznego ładowania dowolnego `ProjectReference` lub `PackageReference` elementów znalezionych w tym `.csproj` czasie w `import qsharp` poleceniu.</span><span class="sxs-lookup"><span data-stu-id="6deba-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="6deba-244">Na przykład poniżej przedstawiono prosty `.csproj` plik, który powoduje Q# automatyczne załadowanie `Microsoft.Quantum.Chemistry` pakietu:</span><span class="sxs-lookup"><span data-stu-id="6deba-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="6deba-245">Obecnie ta właściwość niestandardowa `<IQSharpLoadAutomatically>` jest wymagana przez hosty Python, ale w przyszłości może stać się domyślnym zachowaniem dla `.csproj` pliku znajdującego się w tym samym folderze co skrypt języka Python.</span><span class="sxs-lookup"><span data-stu-id="6deba-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-246">Obecnie `<QsharpCompile>` ustawienie w `.csproj` jest ignorowane przez hosty języka Python, a wszystkie `.qs` pliki w folderze `.csproj` (w tym podfolderach) są ładowane i kompilowane.</span><span class="sxs-lookup"><span data-stu-id="6deba-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="6deba-247">Obsługa `.csproj` ustawień zostanie ulepszona w przyszłości (zobacz [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) , aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="6deba-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="6deba-248">C#</span><span class="sxs-lookup"><span data-stu-id="6deba-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="6deba-249">Program hosta języka C# ma wiele składników i działa bardzo blisko z niektórymi składnikami QDK, takimi jak symulatory, które są wbudowane w języku C#.</span><span class="sxs-lookup"><span data-stu-id="6deba-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="6deba-250">Q#Kompilator działa w tym miejscu przez wygenerowanie równoważnej nazwy przestrzeni nazw C# z Q# przestrzeni nazw w Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="6deba-251">Następnie generuje on równoważną nazwę klasy C# dla każdego obiektu Q# lub zdefiniowanego w nim typu.</span><span class="sxs-lookup"><span data-stu-id="6deba-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="6deba-252">Najpierw udostępniamy wszelkie klasy używane w naszym programie hosta z `using` instrukcjami, które są w przybliżeniu analagous do `open` instrukcji w naszym Q# pliku:</span><span class="sxs-lookup"><span data-stu-id="6deba-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="6deba-253">Następnie deklarujemy naszą przestrzeń nazw języka C#, kilka innych bitów i kawałków (zobacz pełny blok kodu poniżej), a następnie wszelkie klasyczne programowanie, które chcemy (na przykład przetwarzanie argumentów dla wywoływanych danych Q# ).</span><span class="sxs-lookup"><span data-stu-id="6deba-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="6deba-254">Ten ostatni nie jest konieczny w naszym przypadku, ale przykład takiego użycia można znaleźć w  [próbce współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="6deba-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="6deba-255">Maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="6deba-255">Target machines</span></span>

<span data-ttu-id="6deba-256">Po powrocie do programu Q# należy utworzyć wystąpienie dowolnego komputera docelowego, na którym zostaną uruchomione nasze operacje.</span><span class="sxs-lookup"><span data-stu-id="6deba-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="6deba-257">Używanie innych maszyn docelowych jest tak proste jak utworzenie wystąpienia innego, chociaż proces wykonywania operacji i przetwarzania zwrotów może być nieco inny.</span><span class="sxs-lookup"><span data-stu-id="6deba-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="6deba-258">W przypadku usługi zwięzłości dodaliśmy do tej [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pory, a [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [poniżej](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="6deba-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="6deba-259">Każda Klasa języka C# wygenerowana na podstawie Q# operacji ma `Run` metodę, a pierwszy argument, który musi być wystąpieniem maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="6deba-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="6deba-260">Tak, aby działała `MeasureSuperposition` na `QuantumSimulator` , używamy `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="6deba-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="6deba-261">Zwrócone wyniki można następnie przypisać do zmiennych w języku C#:</span><span class="sxs-lookup"><span data-stu-id="6deba-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="6deba-262">`Run`Metoda jest uruchamiana asynchronicznie, ponieważ będzie dotyczyć rzeczywistego sprzętu Quantum, w związku z czym `await` słowo kluczowe blokuje dalsze przetwarzanie do momentu ukończenia zadania.</span><span class="sxs-lookup"><span data-stu-id="6deba-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="6deba-263">Jeśli możliwy do odrzucania Q# nie ma żadnych zwracanych (na przykład zwraca typ `Unit` ), przebieg można nadal wykonać w taki sam sposób, bez przypisywania go do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="6deba-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="6deba-264">W takim przypadku cały wiersz będzie po prostu zawierać</span><span class="sxs-lookup"><span data-stu-id="6deba-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="6deba-265">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6deba-265">Arguments</span></span>

<span data-ttu-id="6deba-266">Wszystkie argumenty do wywoływanych Q# są po prostu przekazane jako dodatkowe argumenty po maszynie docelowej.</span><span class="sxs-lookup"><span data-stu-id="6deba-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="6deba-267">W związku z tym wyniki `MeasureSuperpositionArray` dotyczące `n=4` qubits zostałyby pobrane za pośrednictwem</span><span class="sxs-lookup"><span data-stu-id="6deba-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="6deba-268">Pełny program hosta języka C# może więc wyglądać jak</span><span class="sxs-lookup"><span data-stu-id="6deba-268">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="6deba-269">W lokalizacji pliku C# programu hosta można uruchomić z wiersza polecenia, wprowadzając</span><span class="sxs-lookup"><span data-stu-id="6deba-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="6deba-270">w takim przypadku zobaczysz dane wyjściowe zapisywane w konsoli podobnej do</span><span class="sxs-lookup"><span data-stu-id="6deba-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="6deba-271">Ze względu na współdziałanie kompilatora z przestrzeniami nazw możemy Alternatywnie wykorzystać nasze możliwe do przedzwonienia Q# bez `using NamespaceName;` instrukcji i po prostu dopasowując do niej tytuł przestrzeni nazw języka C#.</span><span class="sxs-lookup"><span data-stu-id="6deba-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="6deba-272">Oznacza to, zamieniając `namespace host` na `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="6deba-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="6deba-273">Łącznie z szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="6deba-273">Including the resources estimator</span></span>

<span data-ttu-id="6deba-274">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Do pobrania danych wyjściowych jest wymagana nieco inna implementacja.</span><span class="sxs-lookup"><span data-stu-id="6deba-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="6deba-275">Po pierwsze, zamiast tworzyć wystąpienia ich jako zmiennej przy użyciu `using` instrukcji (w miarę wykonywania operacji `QuantumSimulator` ), możemy bezpośrednio utworzyć wystąpienia obiektów klasy za pośrednictwem</span><span class="sxs-lookup"><span data-stu-id="6deba-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="6deba-276">Zwróć uwagę, że zamiast pojedynczego symulatora docelowego, który ma być używany przez wiele Q# operacji, został utworzony wystąpienie dla każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="6deba-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="6deba-277">Wynika to z faktu, że obiekty są modyfikowane, gdy są używane jako maszyny docelowe, a ich wyniki można następnie pobrać później przy użyciu metody klasy `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="6deba-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="6deba-278">Aby uruchomić operacje na szacowania zasobów, użyjemy</span><span class="sxs-lookup"><span data-stu-id="6deba-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="6deba-279">a następnie Pobierz wyniki jako wartości rozdzielane znakami tabulacji (TSV) z `estimatorSingleQ.ToTSV()` i `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="6deba-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="6deba-280">Tak więc pełny program hosta w języku C#, który korzysta z obu `QuantumSimulator` i `ResourcesEstimator` może przyjmować formę:</span><span class="sxs-lookup"><span data-stu-id="6deba-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="6deba-281">co da wynik podobny do</span><span class="sxs-lookup"><span data-stu-id="6deba-281">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="6deba-282">Q# Notesy Jupyter</span><span class="sxs-lookup"><span data-stu-id="6deba-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="6deba-283">Q# Notesy Jupyter używają Q# jądra I, które umożliwia definiowanie, kompilowanie i uruchamianie wywoływanych elementów Q# w pojedynczym notesie---wszystkie instrukcje, notatki i inne treści.</span><span class="sxs-lookup"><span data-stu-id="6deba-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="6deba-284">Oznacza to, że chociaż istnieje możliwość zaimportowania i użycia zawartości `*.qs` Q# plików, nie jest to konieczne w modelu uruchomieniowym.</span><span class="sxs-lookup"><span data-stu-id="6deba-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="6deba-285">Tutaj szczegółowo opisano sposób uruchamiania Q# operacji zdefiniowanych powyżej, ale bardziej rozległe wprowadzenie do korzystania z Q# notesów Jupyter jest dostępne na stronie [wprowadzenie do Q# i Jupyter notesów](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="6deba-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="6deba-286">Definiowanie operacji</span><span class="sxs-lookup"><span data-stu-id="6deba-286">Defining operations</span></span>

<span data-ttu-id="6deba-287">W Q# Jupyter Notebook wprowadzasz kod w Q# taki sam sposób jak w przestrzeni nazw Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="6deba-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="6deba-288">Dzięki temu możemy umożliwić dostęp do wywoływanych [ Q# bibliotek standardowych](xref:microsoft.quantum.libraries.standard.intro) za pomocą `open` instrukcji dla odpowiednich przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="6deba-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="6deba-289">Po uruchomieniu komórki z taką instrukcją definicje z tych przestrzeni nazw są dostępne w całym obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="6deba-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-290">Elementy [Microsoft. Quantum.](xref:Microsoft.Quantum.Intrinsic) Inin i [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (na przykład [`H`](xref:Microsoft.Quantum.Intrinsic.H) i [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) są automatycznie dostępne dla operacji zdefiniowanych w komórkach w Q# notesach Jupyter.</span><span class="sxs-lookup"><span data-stu-id="6deba-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="6deba-291">Nie jest to jednak prawdziwe w przypadku kodu pochodzącego z zewnętrznych Q# plików źródłowych (proces pokazywany na początku [ Q# i w notesach Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="6deba-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="6deba-292">Podobnie Definiowanie operacji wymaga tylko pisania Q# kodu i uruchomienia komórki.</span><span class="sxs-lookup"><span data-stu-id="6deba-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="6deba-293">Następnie dane wyjściowe wyświetlają następnie te operacje, które następnie mogą być wywoływane z przyszłych komórek.</span><span class="sxs-lookup"><span data-stu-id="6deba-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="6deba-294">Maszyny docelowe</span><span class="sxs-lookup"><span data-stu-id="6deba-294">Target machines</span></span>

<span data-ttu-id="6deba-295">Funkcje do uruchamiania operacji na konkretnych komputerach docelowych są udostępniane za pomocą [ Q# poleceń Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="6deba-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="6deba-296">Na przykład program `%simulate` korzysta z programu `QuantumSimulator` i korzysta z `%estimate` `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="6deba-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="6deba-297">Przekazywanie danych wejściowych do funkcji i operacji</span><span class="sxs-lookup"><span data-stu-id="6deba-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="6deba-298">Aby przekazać dane wejściowe do Q# operacji, argumenty mogą być przekazywane jako `key=value` pary do polecenia Run Magic.</span><span class="sxs-lookup"><span data-stu-id="6deba-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="6deba-299">W celu uruchomienia `MeasureSuperpositionArray` programu z czterema qubits można uruchomić `%simulate MeasureSuperpositionArray n=4` następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="6deba-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="6deba-300">Ten wzorzec może być używany podobnie z `%estimate` i innymi poleceniami Run.</span><span class="sxs-lookup"><span data-stu-id="6deba-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="6deba-301">Używanie Q# kodu z innych projektów lub pakietów</span><span class="sxs-lookup"><span data-stu-id="6deba-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="6deba-302">Domyślnie Q# Jupyter Notebook ładuje wszystkie `.qs` pliki w bieżącym folderze i wprowadza ich Q# operacje i funkcje dostępne do użycia w notesie.</span><span class="sxs-lookup"><span data-stu-id="6deba-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="6deba-303">[ `%who` Magic polecenie](xref:microsoft.quantum.iqsharp.magic-ref.who) wyświetla listę wszystkich aktualnie dostępnych Q# operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="6deba-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="6deba-304">Aby załadować Q# kod z innego folderu, można użyć [ `%project` polecenia Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) w celu dodania odwołania do `.csproj` pliku dla Q# projektu (czyli projektu, do którego odwołuje się odwołanie `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="6deba-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="6deba-305">To polecenie spowoduje skompilowanie wszystkich `.qs` plików w folderze zawierającym `.csproj` (i podfoldery).</span><span class="sxs-lookup"><span data-stu-id="6deba-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="6deba-306">Spowoduje również cykliczne załadowanie wszelkich pakietów, do których odwołuje się `PackageReference` lub Q# projekty, do których odwołuje się `ProjectReference` ten `.csproj` plik.</span><span class="sxs-lookup"><span data-stu-id="6deba-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="6deba-307">Przykładowo następujące komórki symulują Q# operację z zewnętrznego projektu, gdzie Ścieżka projektu jest przywoływana względem bieżącego folderu:</span><span class="sxs-lookup"><span data-stu-id="6deba-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="6deba-308">Aby załadować pakiety zewnętrzne zawierające Q# kod, użyj [ `%package` polecenia Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="6deba-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="6deba-309">Załadowanie pakietu spowoduje również udostępnienie wszelkich niestandardowych poleceń magicznych lub koderów, które są zawarte w zestawach, które są częścią pakietu.</span><span class="sxs-lookup"><span data-stu-id="6deba-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="6deba-310">Aby załadować pakiety zewnętrzne lub Q# projekty w programie Notes czasu dostarczenie, upewnij się, że folder Notes zawiera `.csproj` plik, którego dotyczy odwołanie `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="6deba-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="6deba-311">W tym `.csproj` celu należy dodać właściwość `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="6deba-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="6deba-312">Spowoduje to Q# załadowanie rekursywnie dowolnego `ProjectReference` lub `PackageReference` elementów znalezionych w tym `.csproj` czasie podczas ładowania notesu.</span><span class="sxs-lookup"><span data-stu-id="6deba-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="6deba-313">Na przykład poniżej przedstawiono prosty `.csproj` plik, który powoduje Q# automatyczne załadowanie `Microsoft.Quantum.Chemistry` pakietu:</span><span class="sxs-lookup"><span data-stu-id="6deba-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="6deba-314">Obecnie ta właściwość niestandardowa `<IQSharpLoadAutomatically>` jest wymagana przez Q# Jupyter Notebook hosty, ale w przyszłości może to być zachowanie domyślne dla `.csproj` pliku znajdującego się w tym samym folderze, w którym znajduje się plik notesu.</span><span class="sxs-lookup"><span data-stu-id="6deba-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="6deba-315">Obecnie `<QsharpCompile>` ustawienie w `.csproj` jest ignorowane przez Q# Jupyter Notebook hosty, a wszystkie `.qs` pliki w folderze `.csproj` (w tym podfolderach) są ładowane i kompilowane.</span><span class="sxs-lookup"><span data-stu-id="6deba-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="6deba-316">Obsługa `.csproj` ustawień zostanie ulepszona w przyszłości (zobacz [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) , aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="6deba-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
