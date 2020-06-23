---
title: Symulatory kwantowe i aplikacje hosta | Microsoft Docs
description: Opis tworzenia symulatorów kwantowych przy użyciu klasycznego języka platformy .NET (zazwyczaj C# lub Q#).
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273804"
---
# <a name="quantum-simulators-and-host-applications"></a>Symulatory kwantowe i aplikacje hosta

## <a name="what-youll-learn"></a>Zawartość

> [!div class="checklist"]
> * Jak są wykonywane algorytmy kwantowe
> * Jakie symulatory kwantowe są zawarte w tej wersji
> * Jak napisać sterownik C# dla algorytmu kwantowego

## <a name="the-quantum-development-kit-execution-model"></a>Model wykonywania zestawu Quantum Development Kit

W artykule [Pisanie programu kwantowego](xref:microsoft.quantum.write-program) algorytm kwantowy był wykonywany przez przekazanie obiektu `QuantumSimulator` do metody `Run` klasy algorytmu.
Klasa `QuantumSimulator` umożliwia wykonanie algorytmu kwantowego dzięki pełnej symulacji wektora stanu kwantowego, który doskonale nadaje się do uruchamiania i testowania przykładu `Teleport`.
Aby uzyskać więcej informacji na temat wektorów stanów kwantowych, zobacz [Przewodnik po pojęciach](xref:microsoft.quantum.concepts.intro).

Algorytm kwantowy można uruchamiać na innych maszynach docelowych.
Maszyna zapewnia implementacje kwantowych typów pierwotnych algorytmu.
Obejmują one operacje pierwotne, takie jak H, CNOT i Measure, a także śledzenie kubitów i zarządzanie nimi.
Poszczególne klasy maszyn kwantowych reprezentują różne modele wykonywania tego samego algorytmu kwantowego.

Każdy typ maszyny kwantowej może udostępniać odrębną implementację typów pierwotnych.
Na przykład zawarty w zestawie deweloperskim symulator śledzenia komputera kwantowego nie służy do wykonywania symulacji.
Zamiast tego śledzi on użycie bramy, kubitów oraz innych zasobów.

### <a name="quantum-machines"></a>Maszyny kwantowe

W przyszłości zostaną zdefiniowane dodatkowe klasy maszyn kwantowych umożliwiające obsługę innych typów symulacji oraz wykonywanie na topologicznych komputerach kwantowych.
Zapewnienie niezmienności algorytmu przy różnych bazowych implementacjach na maszynach ułatwia jego testowanie i debugowanie w symulacji, a następnie uruchamianie na używanym komputerze z poczuciem pewności, że nie został zmieniony.

### <a name="whats-included-in-this-release"></a>Zawartość tej wersji

Ta wersja zestawu Quantum Development Kit zawiera kilka klas maszyn kwantowych.
Każda klasa jest zdefiniowana w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators`.

* Klasa `QuantumSimulator`, [symulator wektora pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator).
* Klasa `ResourcesEstimator`, [proste narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator), umożliwia ogólną analizę zasobów wymaganych do uruchomienia algorytmu kwantowego.
* Klasa `QCTraceSimulator`, [oparte na śledzeniu narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.qc-trace-simulator.intro), umożliwia zaawansowaną analizę zużycia zasobów dla całego grafu wywołań algorytmu.
* Klasa `ToffoliSimulator`, [symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).

## <a name="writing-a-host-application"></a>Pisanie aplikacji hosta

W artykule [Pisanie programu kwantowego](xref:microsoft.quantum.write-program) napisaliśmy prosty sterownik w języku C# dla algorytmu teleportacji. Sterownik w języku C# ma 4 główne funkcje:

* Konstruowanie maszyny docelowej
* Obliczanie wszystkich argumentów wymaganych przez algorytm kwantowy
* Uruchamianie algorytmu kwantowego przy użyciu symulatora
* Przetwarzanie wyniku operacji

Poniżej szczegółowo omówiono poszczególne etapy.

### <a name="constructing-the-target-machine"></a>Konstruowanie maszyny docelowej

Maszyny kwantowe to normalne wystąpienia klas .NET, dlatego tworzy się je przez wywołanie konstruktora, tak jak w przypadku dowolnej klasy .NET.
Niektóre symulatory, w tym `QuantumSimulator`, implementują interfejs .NET <xref:System.IDisposable?displayProperty=nameWithType>, dlatego należy je umieścić w instrukcji `using` języka C#.

### <a name="computing-arguments-for-the-algorithm"></a>Obliczanie argumentów dla algorytmu

W naszym przykładzie `Teleport` obliczyliśmy kilka względnie sztucznych argumentów przekazywanych do algorytmu kwantowego.
Zwykle jednak algorytm kwantowy wymaga znacznej ilości danych i najłatwiej je udostępnić z poziomu klasycznego sterownika.

Na przykład w przypadku symulacji chemicznych algorytm kwantowy wymaga dużej tabeli wartości całkowitych dotyczących orbitalnych interakcji molekuł.
Zazwyczaj informacje te są odczytywane z pliku, który jest dostarczany podczas uruchamiania algorytmu.
Język Q# nie udostępnia mechanizmu uzyskiwania dostępu do systemu plików, dlatego najlepiej jest zebrać takie dane przy użyciu klasycznego sterownika, a następnie przekazać je do metody `Run` algorytmu kwantowego.

Klasyczny sterownik odgrywa również kluczową rolę w metodach zmiennych.
W tej klasie algorytmów na podstawie klasycznych parametrów przygotowuje się stan kwantowy, a następnie używa się go do obliczenia jakiejś wartości.
Parametry są dostosowywane na podstawie określonego algorytmu wspinaczki lub algorytmu uczenia maszynowego, a następnie algorytm kwantowy jest uruchamiany ponownie.
Algorytm wspinaczki najlepiej jest zaimplementować jako czysto klasyczną funkcję, wywoływaną przez klasyczny sterownik. Wyniki procesu wspinaczki są następnie przekazywane do następnego przebiegu algorytmu kwantowego.

### <a name="running-the-quantum-algorithm"></a>Uruchamianie algorytmu kwantowego

Ta część jest ogólnie bardzo prosta.
Każda operacja języka Q# jest powiązana ze skompilowaną klasą, która udostępnia metodę statyczną `Run`.
Argumenty tej metody są udostępniane przez spłaszczoną krotkę argumentów samej operacji. Dodatkowy, pierwszy argument jest symulatorem umożliwiającym wykonywanie. Spłaszczony odpowiednik operacji, która oczekuje nazwanej krotki typu `(a: String, (b: Double, c: Double))`, to `(String a, Double b, Double c)`.


Przekazując argumenty do metody `Run`, trzeba pamiętać o kilku kwestiach:

* Tablice muszą być opakowane w obiekt `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Klasa `QArray` ma konstruktor, który przyjmuje dowolną uporządkowaną kolekcję (`IEnumerable<T>`) odpowiednich obiektów.
* Pusta krotka, `()` w języku Q#, jest reprezentowana przez element `QVoid.Instance` w języku C#.
* Niepuste krotki są reprezentowane jako wystąpienia `ValueTuple` programu .NET.
* Zdefiniowane przez użytkownika typy języka Q# są przekazywane jako typy podstawowe.
* Aby przekazać operację lub funkcję do metody `Run`, należy uzyskać wystąpienie klasy operacji lub funkcji przy użyciu metody `Get<>` symulatora.

### <a name="processing-the-results"></a>Przetwarzanie wyników

Wyniki algorytmu kwantowego są zwracane z metody `Run`.
Metoda `Run` jest wykonywana asynchronicznie, dlatego zwraca wystąpienie klasy <xref:System.Threading.Tasks.Task`1>.
Istnieje wiele sposobów uzyskiwania rzeczywistych wyników operacji. Najprostszym z nich jest użycie właściwości [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) klasy `Task`:

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
Można jednak użyć innych technik, takich jak użycie metody [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) lub słowa kluczowego [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) języka C#.

Podobnie jak w przypadku argumentów, krotki języka Q# są reprezentowane jako wystąpienia `ValueTuple`, a tablice języka Q# są reprezentowane jako wystąpienia `QArray`.
Typy zdefiniowane przez użytkownika są zwracane jako typy podstawowe.
Pusta krotka `()` jest zwracana jako wystąpienie klasy `QVoid`.

Wiele algorytmów kwantowych wymaga rozbudowanego przetwarzania końcowego w celu uzyskania użytecznych odpowiedzi.
Na przykład kwantowa część algorytmu Shora jest tylko początkiem obliczeń, które umożliwiają rozłożenie liczby na czynniki.

W większości przypadków takie przetwarzanie końcowe najłatwiej jest zrealizować w klasycznym sterowniku.
Udostępnienie wyników użytkownikowi lub zapisanie ich na dysku jest możliwe tylko za pomocą klasycznego sterownika.
Klasyczny sterownik ma dostęp do bibliotek analitycznych i innych funkcji matematycznych, które nie są dostępne w języku Q#.


## <a name="failures"></a>Błędy

Gdy podczas operacji nastąpi wykonywanie instrukcji `fail` języka Q#, zostanie zgłoszony wyjątek `ExecutionFailException`.

Ze względu na użycie klasy `System.Task` w metodzie `Run` wyjątek zgłoszony w wyniku instrukcji `fail` zostanie opakowany w klasę `System.AggregateException`.
Aby znaleźć faktyczną przyczynę błędu, należy wykonać iterację we właściwości `AggregateException` 
`InnerExceptions`, na przykład:

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

## <a name="other-classical-languages"></a>Inne języki klasyczne

Podane przykłady zostały napisane w językach C#, F# i Python, ale zestaw Quantum Development Kit obsługuje także pisanie programów klasycznych hostów w innych językach.
[Można na przykład napisać](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net) program hosta w języku Visual Basic.
