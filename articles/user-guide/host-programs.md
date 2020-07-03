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
# <a name="ways-to-run-a-q-program"></a>Sposoby uruchamiania programu Q #

Jednym z największych zalet zestawu Quantum Development Kit jest elastyczność między platformami i środowiskami programistycznymi.
Oznacza to jednak, że nowi użytkownicy Q # mogą odmylić lub przeciążyć wiele opcji dostępnych w [przewodniku instalacji](xref:microsoft.quantum.install).
Na tej stronie wyjaśnimy, co się dzieje w przypadku uruchomienia programu Q # i porównać różne sposoby, w których użytkownicy mogą to robić.

Podstawowa różnica polega na tym, że można uruchomić Q #:
- jako aplikacja autonomiczna, gdzie Q # jest jedynym używanym językiem i program jest wywoływany bezpośrednio. Dwie metody faktycznie należą do tej kategorii:
  - Interfejs wiersza polecenia
  - Notesy programu Jupyter dla języka Q#
- za pomocą dodatkowego *programu hosta*, pisanego w języku Python lub języka .NET (np. C# lub F #), który następnie wywołuje program i może dodatkowo przetwarzać wyniki zwrócone.

Aby zapoznać się z najlepszymi procesami i ich różnicami, należy wziąć pod uwagę prosty program Q # i porównać sposoby jego wykonywania.

## <a name="basic-q-program"></a>Basic Q # program

Podstawowy program Quantum może składać się z przygotowania qubit w równej nadmiaru Stanów $ \ket {0} $ i $ \ket {1} $, mierzenia go i zwracania wyniku, który będzie losowo jednym z tych dwóch Stanów z równym prawdopodobieństwem.
W rzeczywistości ten proces jest na początku przewodnika Szybki Start dla [generatora liczb losowych](xref:microsoft.quantum.quickstarts.qrng) .

W polu Q # można wykonać następujące czynności:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Jednak ten kod nie może być wykonywany przez Q #.
W tym celu należy wykonać treść [operacji](xref:microsoft.quantum.guide.basics#q-operations-and-functions), która jest następnie wykonywana, gdy wywoływana---albo bezpośrednio lub przez inną operację. W związku z tym można napisać operację w następującej postaci:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Zdefiniowano operację, `MeasureSuperposition` która nie pobiera danych wejściowych i zwraca wartość typu [Result](xref:microsoft.quantum.guide.types).

Chociaż przykłady na tej stronie składają się tylko z *operacji*q #, wszystkie koncepcje, które będziemy omawiać, odnoszą się również do *funkcji*q # i dlatego odwołują się do nich w sposób, *w jaki są*wywoływane. Różnice między nimi są omówione w sekcji [p # podstawowe: operacje i funkcje](xref:microsoft.quantum.guide.basics#q-operations-and-functions)oraz więcej szczegółowych informacji na temat ich definiowania można znaleźć w temacie [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-q-file"></a>Możliwe do przedefiniowania w pliku Q #

Wywołanie jest precyzyjnie wywoływane i uruchamiane przez Q #.
Jednak wymaga to jeszcze kilku dodatkowych uzupełnień, które składają się na pełny `*.qs` plik Q #.

Wszystkie typy i wartościowe elementy Q # są zdefiniowane w *przestrzeni nazw*, co zapewnia pełną nazwę, do której można się odwoływać.

Na przykład [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operacje i są dostępne w [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) przestrzeniach nazw i (część [bibliotek Q # Standard](xref:microsoft.quantum.qsharplibintro)).
W związku z tym zawsze można je wywoływać za pośrednictwem ich *pełnych* nazw, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale zawsze będzie to miało nieczytelny kod.

Zamiast tego `open` instrukcje umożliwiają wywoływanie z bardziej zwięzłą składnią skróconą, jak zostało to zrobione w powyższej treści operacji.
Pełny plik Q # zawierający naszą operację powinien w związku z tym zawierać definicje naszej przestrzeni nazw, otwierając przestrzenie nazw dla tych, których używa nasza operacja, a następnie naszej operacji:

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
> W przypadku otwarcia przestrzeni nazw można również uzyskać *aliasy* , co może być przydatne w przypadku, gdy w dwóch obszarach nazw występuje konflikt nazw.
> Na przykład zamiast tego możemy użyć `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` powyżej, a następnie wywołać metodę `H` `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Jedynym wyjątkiem jest [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) przestrzeń nazw, która jest zawsze automatycznie otwierana.
> W związku z tym możliwe jest, że takie wywoływanie [`Length`](xref:microsoft.quantum.core.length) może być zawsze używane bezpośrednio.

### <a name="execution-on-target-machines"></a>Wykonywanie na komputerach docelowych

Teraz ogólny model wykonywania programu Q # zostanie wyczyszczony.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Po pierwsze, konkretnie wywoływane do wykonania ma dostęp do wszelkich innych metod i typów zdefiniowanych w tej samej przestrzeni nazw.
Uzyskują również dostęp do elementów z dowolnej [biblioteki Q #](xref:microsoft.quantum.libraries), ale muszą one być przywoływane za pośrednictwem ich pełnej nazwy lub za pomocą `open` instrukcji opisanych powyżej.

Samo wywoływanie jest wykonywane na *[maszynie docelowej](xref:microsoft.quantum.machines)*.
Takie maszyny docelowe mogą być rzeczywistym sprzętem Quantum lub wieloma symulatorami dostępnymi jako część QDK.
W naszym przykładzie najbardziej przydatną maszyną docelową jest wystąpienie [symulatora o pełnym stanie](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` która oblicza zachowanie programu tak, jakby było wykonywane na komputerze z systemem Quantum z nieprawidłowym hałasem.

Do tej pory opisano, co się dzieje w przypadku wykonywania określonych pytań typu Q #.
Bez względu na to, czy Q # jest używany w aplikacji autonomicznej, czy za pomocą programu hosta, ten ogólny proces jest większy lub mniejszy---w związku z tym elastyczność QDK.
Różnice między różnymi sposobami wywołania zestawu Quantum Development Kit w ten sposób ujawniają się w *sposób* , w jaki wywołania Q # są wywoływane do wykonania i w jaki sposób są zwracane wszystkie wyniki.
Bardziej szczegółowe różnice między nimi 
1. wskazuje, które polecenie Q # można wykonać,
2. jak są udostępniane potencjalną liczbę argumentów,
3. Określanie komputera docelowego, na którym ma zostać wykonane jego wykonywanie, oraz
4. sposób zwracania wyników.

Najpierw omówiono, jak to zrobić za pomocą aplikacji autonomicznej Q # z wiersza polecenia, a następnie kontynuować pracę z programami hosta Python i C#.
Firma Microsoft rezerwuje autonomiczną aplikację dla notesów Q # Jupyter w ciągu ostatnich, ponieważ w przeciwieństwie do pierwszych trzech funkcja podstawowa nie Wyśrodkowuje całego lokalnego pliku Q #.

> [!NOTE]
> Chociaż nie jest to zilustrowane w tych przykładach, jedna ze współdziałania między metodami wykonywania polega na tym, że wszystkie komunikaty, które są drukowane z wewnątrz programu Q # ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) na przykład), zazwyczaj zawsze będą drukowane do odpowiedniej konsoli.

## <a name="q-from-the-command-line"></a>Q # z wiersza polecenia
Jednym z najprostszych sposobów rozpoczęcia pisania p # programy jest uniknięcie przejmowania się niezależnymi plikami i drugim językiem.
Używanie Visual Studio Code lub programu Visual Studio z rozszerzeniem QDK umożliwia bezproblemowe przepływ pracy, w którym firma Microsoft jest uruchamiana z tylko jednym plikiem Q #.

W ten sposób ostatecznie wywołamy wykonanie programu, wprowadzając
```dotnetcli
dotnet run
```
w wierszu polecenia.
Najprostszym przepływem pracy jest to, że lokalizacja katalogu terminalu jest taka sama jak w przypadku pliku Q #, który można łatwo obsłużyć podczas edycji pliku Q # przy użyciu zintegrowanego terminalu w VS Code, na przykład.
Jednak [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje wiele opcji, a program może być również uruchamiany z innej lokalizacji, po prostu dostarczając `--project <PATH>` lokalizację pliku Q #.


### <a name="add-entry-point-to-q-file"></a>Dodaj punkt wejścia do pliku Q #

Większość plików Q # będzie zawierać więcej niż jeden możliwy do przekroczenia, dlatego musimy poinformować kompilator o *tym, który* jest możliwy do wykonania, gdy udostępnimy `dotnet run` polecenie.
Jest to wykonywane z prostą zmianą w pliku Q #: 
    - Dodaj wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do odwoływać.

Nasz plik z powyższych woli stać się
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

Teraz wywołanie `dotnet run` z wiersza polecenia prowadzi do `MeasureSuperposition` uruchomienia, a zwracana wartość jest następnie drukowana bezpośrednio do terminalu.
W związku z tym zobaczysz `One` lub `Zero` Wydrukowano. 

Należy pamiętać, że nie ma znaczenia, czy masz więcej żądanych, zdefiniowanych poniżej, tylko `MeasureSuperposition` zostanie uruchomiony.
Ponadto nie jest to problem, jeśli Twoje wywoływane dane zawierają [Komentarze dokumentacji](xref:microsoft.quantum.guide.filestructure#documentation-comments) przed jej deklaracją, `@EntryPoint()` atrybut może być po prostu umieszczony nad nimi.

### <a name="callable-arguments"></a>Wywoływane argumenty

Do tej pory uważamy tylko operację, która nie pobiera danych wejściowych.
Załóżmy, że chcemy wykonać podobną operację, ale na wielu qubits---liczbę, która jest dostarczana jako argument.
Taka operacja może być zapisywana jako
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
gdzie zwrócona wartość jest tablicą wyników pomiaru.
Należy zauważyć, że [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) i [`ForEach`](xref:microsoft.quantum.arrays.foreach) znajdują się w [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) przestrzeniach nazw i wymaga dodatkowych `open` instrukcji dla każdego z nich.

Jeśli przeniesiemy `@EntryPoint()` atrybut, aby poprzedzał tę nową operację (należy pamiętać, że w pliku może znajdować się tylko jeden wiersz), a próba uruchomienia go z prostu powoduje wyświetlenie `dotnet run` komunikatu o błędzie, który wskazuje, jakie dodatkowe opcje wiersza polecenia są wymagane i jak je przedstawić.

Ogólny format wiersza polecenia jest w rzeczywistości i w `dotnet run [options]` tym miejscu są dostępne argumenty.
W takim przypadku `n` Brak argumentu i pokazuje, że musimy podać opcję `-n <n>` . W `MeasureSuperpositionArray` związku z `n=4` tym qubits

```dotnetcli
dotnet run -n 4
```

zwraca dane wyjściowe podobne do

```output
[Zero,One,One,One]
```

Ten kurs rozciąga się na wiele argumentów.

> [!NOTE]
> Nazwy argumentów zdefiniowane w programie `camelCase` są nieco modyfikowane przez kompilator, który ma zostać zaakceptowany jako dane wejściowe Q #. Na przykład, jeśli zamiast `n` , użyto `numQubits` powyższej nazwy, to dane wejściowe byłyby dostępne w wierszu polecenia `--num-qubits 4` zamiast `-n 4` .

Komunikat o błędzie zawiera również inne opcje, które mogą być używane, w tym informacje o sposobie zmiany maszyny docelowej.

### <a name="different-target-machines"></a>Różne maszyny docelowe

Ponieważ dane wyjściowe naszych operacji zostały z tego względu oczekiwane wyniki ich działania w realnej qubits, jest to oczywiste, że domyślną maszyną docelową z wiersza polecenia jest quauntum symulator, `QuantumSimulator` .
Można jednak wydać możliwość uruchomienia na konkretnym komputerze docelowym z opcją `--simulator` (lub skrótem `-s` ).

Można na przykład uruchomić ją na [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

Drukowane dane wyjściowe są następnie

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

Aby uzyskać szczegółowe informacje na temat tego, co wskazują te metryki, zobacz [Resource szacowania: raportowane metryki](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Podsumowanie wykonania wiersza polecenia
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Opcje inne niż Q # `dotnet run`

Jak opisano powyżej przy użyciu `--project` opcji, [ `dotnet run` polecenie](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) akceptuje również opcje niepowiązane z argumentami Q #, które można wywołać.
W przypadku udostępniania obu rodzajów opcji `dotnet` należy najpierw podać opcje specyficzne, po których następuje ogranicznik `--` , a następnie opcje dotyczące opcji Q.
Na przykład specifiying ścieżka wraz z liczbą qubits dla operacji powyżej zostanie wykonana za pośrednictwem `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Q # z programami hosta

Dzięki naszemu plikowi Q # alternatywą do wywołania operacji lub funkcji bezpośrednio z wiersza polecenia jest użycie *programu hosta* w innym klasycznym języku. W szczególności można to zrobić za pomocą języka Python lub środowiska .NET, takiego jak C# lub F # (na przykład w przypadku zwięzłości w tym miejscu zostanie przedstawione szczegółowe informacje dotyczące języka C#).
Aby włączyć współdziałanie, wymagana jest nieco większa konfiguracja, ale te szczegóły znajdują się w [przewodnikach instalacji](xref:microsoft.quantum.install).

W Nutshell sytuacja obejmuje teraz plik programu hosta (np. `*.py` lub `*.cs` ) w tej samej lokalizacji, w której znajduje się plik Q #.
Teraz jest to program *hosta* , który jest uruchamiany i w trakcie jego wykonywania może wywoływać określone operacje Q # i funkcje z pliku Q #.
Rdzeń współdziałania jest oparty na kompilatorze Q #, dzięki czemu zawartość pliku Q # jest dostępna dla programu hosta, dzięki czemu mogą one być wywoływane.

Jedną z głównych zalet korzystania z programu hosta jest to, że klasyczne dane zwrócone przez program Q # można następnie przetworzyć w języku hosta.
Może to obejmować pewne zaawansowane przetwarzanie danych (np. coś, które nie może być wykonane wewnętrznie w pytaniach Q #), a następnie wywoływanie dalszych akcji Q # na podstawie tych wyników, jak również do wykreślania wyników Q #.

Ogólny schemat jest przedstawiony tutaj i omawiamy konkretne implementacje dla języków Python i C#. Przykład przy użyciu programu hosta języka F # można znaleźć na [Przykłady współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Atrybut używany dla aplikacji wiersza polecenia Q # nie może być używany z programami hosta.
> Jeśli jest obecny w pliku Q # wywoływanego przez hosta, zostanie zgłoszony błąd. 

Do pracy z różnymi programami hosta nie są wymagane żadne zmiany w `*.qs` pliku Q #.
Następujące implementacje programu hosta działają z tym samym plikiem Q #:

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

Wybierz kartę odpowiadającą posiadanym językiem hosta.

### <a name="python"></a>[Python](#tab/tabid-python)
Program hosta języka Python jest skonstruowany w następujący sposób:
1. Zaimportuj `qsharp` moduł, który rejestruje moduł ładujący modułów pod kątem współdziałania Q. 
    Dzięki temu obszary nazw Q # mają być wyświetlane jako moduły języka Python, z których można "zaimportować" pytania Q.
    Należy zauważyć, że nie jest to technicznie zgodne z, które są importowane, ale raczej elementy zastępcze języka Python, które umożliwiają wywoływanie tych funkcji.
    Są one zachowane jako obiekty klas języka Python, na których używamy metod do określenia maszyn docelowych do wysyłania operacji do wykonania.

2. Zaimportuj te pytania Q #, które zostaną bezpośrednio wywołane---w tym przypadku, `MeasureSuperposition` i `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Po `qsharp` zaimportowaniu modułu można także zaimportować możliwe do odwoływać się bezpośrednio z przestrzeni nazw biblioteki Q #.

3. W przypadku każdego innego kodu w języku Python można teraz wywołać te, które są wywoływane na określonych maszynach docelowych, i przypisać zwroty do zmiennych (jeśli zwracają wartość) do dalszych użycia.

#### <a name="specifying-target-machines"></a>Określanie maszyn docelowych
Wywołanie operacji do uruchomienia na określonej maszynie docelowej odbywa się za pośrednictwem różnych metod języka Python dla zaimportowanego obiektu.
Na przykład program `.simulate(<args>)` używa `QuantumSimulator` do uruchamiania operacji, a tym `.estimate_resources(<args>)` samym na `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Przekazywanie danych wejściowych do Q\#
Argumenty dla elementu Q # można podać w postaci argumentu słowa kluczowego, gdzie słowo kluczowe jest nazwą argumentu w definicji o wartości Q #.
Oznacza to, że `MeasureSuperpositionArray.simulate(n=4)` jest prawidłowy, a w rezultacie zgłosi `MeasureSuperpositionArray.simulate(4)` błąd.

W związku z tym program hosta Python 

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

wyniki są podobne do następujących:

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Program hosta języka C# ma wiele składników i działa bardzo blisko z niektórymi składnikami QDK, takimi jak symulatory, które są wbudowane w języku C#.

Kompilator Q # działa w tym miejscu przez wygenerowanie równoważnej nazwy przestrzeni nazw C# z przestrzeni nazw Q # w naszym pliku Q #.
Następnie generuje on równoważną nazwę klasy języka C# dla każdej z elementów, które są zdefiniowane w tym polu.

Najpierw udostępniamy wszelkie klasy używane w naszym programie hosta z `using` instrukcjami, które są w przybliżeniu analagous do `open` instrukcji w naszym pliku Q #:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Następnie deklarujemy naszą przestrzeń nazw języka C#, kilka innych bitów i kawałków (zobacz pełny blok kodu poniżej), a następnie wszelkie klasyczne programowanie, które chcemy (np. przetwarzanie argumentów dla zgłaszanych elementów Q #).
Ten ostatni nie jest konieczny w naszym przypadku, ale przykład takiego użycia można znaleźć w [próbce współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Maszyny docelowe

Po powrocie do pytania Q należy utworzyć wystąpienie dowolnego komputera docelowego, na którym będą wykonywane nasze operacje.

```csharp
            using var sim = new QuantumSimulator();
```

Używanie innych maszyn docelowych jest tak proste jak utworzenie wystąpienia innego, chociaż proces wykonywania operacji i przetwarzania zwrotów może być nieco inny.
W przypadku usługi zwięzłości dodaliśmy do tej [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pory, a [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [poniżej](#including-the-resources-estimator).

Każda Klasa języka C# wygenerowana na podstawie operacji Q # ma `Run` metodę, a pierwszy argument, który musi być wystąpieniem maszyny docelowej.
Tak, aby działała `MeasureSuperposition` na `QuantumSimulator` , używamy `MeasureSuperposition.Run(sim)` .
Zwrócone wyniki można następnie przypisać do zmiennych w języku C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Metoda jest wykonywana asynchronicznie, ponieważ będzie to miało miejsce w przypadku rzeczywistego sprzętu Quantum, w związku z czym `await` słowo kluczowe blokuje dalsze wykonywanie do momentu ukończenia zadania.

Jeśli funkcja Q # nie ma żadnych funkcji Return (tj. ma zwracany typ `Unit` ), wykonanie może być nadal wykonywane w taki sam sposób, bez przypisywania go do zmiennej.
W takim przypadku cały wiersz będzie po prostu zawierać 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumenty

Wszystkie argumenty dla wywoływanej wartości Q # są po prostu przekazane jako dodatkowe argumenty po maszynę docelową.
W związku z tym wyniki `MeasureSuperpositionArray` dotyczące `n=4` qubits zostałyby pobrane za pośrednictwem 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Pełny program hosta języka C# może więc wyglądać jak

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

W lokalizacji pliku C# programu hosta można uruchomić z wiersza polecenia, wprowadzając
```dotnetcli
dotnet run
```
w takim przypadku zobaczysz dane wyjściowe zapisywane w konsoli podobnej do 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Ze względu na współdziałanie kompilatora z przestrzeniami nazw możemy Alternatywnie udostępnić nasze Q #, które nie są dostępne bez `using NamespaceName;` instrukcji i po prostu dopasowując do niej tytuł przestrzeni nazw języka C#.
> Oznacza to, zamieniając `namespace host` na `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Łącznie z szacowania zasobów

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Do pobrania danych wyjściowych jest wymagana nieco inna implementacja.

Po pierwsze, zamiast tworzyć wystąpienia ich jako zmiennej przy użyciu `using` instrukcji (w miarę wykonywania operacji `QuantumSimulator` ), możemy bezpośrednio utworzyć wystąpienia obiektów klasy za pośrednictwem

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Zwróć uwagę, że zamiast pojedynczego symulatora docelowego, który ma być używany przez wiele operacji Q #, został utworzony wystąpienie dla każdej z nich. Wynika to z faktu, że obiekty są modyfikowane, gdy są używane jako maszyny docelowe, a ich wyniki można następnie pobrać później przy użyciu metody klasy `.ToTSV()` .

Aby uruchomić operacje na szacowania zasobów, użyjemy

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
a następnie Pobierz wyniki jako wartości rozdzielane znakami tabulacji (TSV) z `estimatorSingleQ.ToTSV()` i `estimatorMultiQ.ToTSV()` .

Tak więc pełny program hosta w języku C#, który korzysta z obu `QuantumSimulator` i `ResourcesEstimator` może przyjmować formę:

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


co da wynik podobny do

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

## <a name="q-jupyter-notebooks"></a>Notesy programu Jupyter dla języka Q#
Notesy q # Jupyter używają jądra IQ #, który umożliwia definiowanie, kompilowanie i uruchamianie niemożliwych dla jednego notesu błędów Q #,---wszystkie instrukcje, notatki i inne elementy.
Oznacza to, że chociaż istnieje możliwość zaimportowania i użycia zawartości `*.qs` plików Q #, nie jest to konieczne w modelu wykonywania.

Tutaj szczegółowo opisano sposób uruchamiania operacji Q # zdefiniowanych powyżej, ale bardziej rozległe wprowadzenie do korzystania z notesów Q # Jupyter jest dostępne na stronie [wprowadzenie do notesów q # i Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definiowanie operacji

W programie Q # Jupyter Notebook wprowadzasz kod Q #, tak jak będziemy z przestrzeni nazw pliku Q #.

Dzięki temu możemy umożliwić dostęp do wywoływanych z [bibliotek Q # Standard](xref:microsoft.quantum.qsharplibintro) za pomocą `open` instrukcji dla odpowiednich przestrzeni nazw.
Po uruchomieniu komórki z taką instrukcją definicje z tych przestrzeni nazw są dostępne w całym obszarze roboczym.

> [!NOTE]
> Elementy [Microsoft. Quantum. wewnętrzne](xref:microsoft.quantum.intrinsic) i [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (np. [`H`](xref:microsoft.quantum.intrinsic.h) i [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) są automatycznie dostępne dla operacji zdefiniowanych w komórkach w notesach Q # Jupyter.
> Nie jest to jednak prawdziwe w przypadku kodu pochodzącego z zewnętrznych plików Q # Source (proces pokazywany na [wprowadzenie do notesów q # i Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Podobnie Definiowanie operacji wymaga tylko zapisania kodu Q # i uruchomienia komórki.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

Następnie dane wyjściowe wyświetlają następnie te operacje, które następnie mogą być wywoływane z przyszłych komórek.

### <a name="target-machines"></a>Maszyny docelowe

Funkcje do uruchamiania operacji na określonych komputerach docelowych są udostępniane za pośrednictwem [poleceń IQ # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).
Na przykład program `%simulate` korzysta z programu `QuantumSimulator` i korzysta z `%estimate` `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Przekazywanie danych wejściowych do funkcji i operacji

Obecnie poleceń Magic wykonywania można używać tylko z operacjami, które nie przyjmują argumentów. Aby uruchomić `MeasureSuperpositionArray` , musimy zdefiniować operację otoki, która następnie wywołuje operację z argumentami:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Ta operacja może być używana podobnie z `%estimate` i innymi poleceniami wykonywania.
