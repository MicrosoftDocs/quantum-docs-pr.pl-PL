---
title: Zasoby Quantum szacowania-Quantum Development Kit
description: Dowiedz się więcej o programie Microsoft QDKe szacowania, który szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze z systemem Quantum.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604647"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Zasoby zestawu Quantum Development Kit (QDK) szacowania

Jak nazwa oznacza, `ResourcesEstimator` Klasa szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze Quantum. Jest to wykonywane przez uruchomienie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu szacuje zasoby dla Q# operacji, które korzystają z tysięcy qubits, pod warunkiem, że klasyczna część kodu jest uruchamiana w rozsądnym czasie.

Szacowania zasobów jest oparty na [symulatorze śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), który zapewnia bogatszy zestaw metryk i narzędzi ułatwiających debugowanie Q# programów.

## <a name="invoking-and-running-the-resources-estimator"></a>Wywoływanie i uruchamianie zasobów szacowania

Możesz użyć szacowania zasobów do uruchomienia dowolnej Q# operacji. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania Q# programu](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Wywoływanie zasobów szacowania z języka C # 

Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie klasy `ResourcesEstimator`, a następnie przekazać je jako pierwszy parametr metody operacji `Run`.

Należy pamiętać, że w przeciwieństwie do klasy `QuantumSimulator` klasa `ResourcesEstimator` nie implementuje interfejsu <xref:System.IDisposable>, dlatego nie trzeba go umieszczać w instrukcji `using`.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę, która generuje tabelę z wartościami rozdzielonymi tabulatorami (tsv). Tabelę można zapisać w pliku lub wyświetlić w konsoli programu na potrzeby analizy. Poniżej przedstawiono przykładowe dane wyjściowe z poprzedniego programu:

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> `ResourcesEstimator`Wystąpienie nie resetuje obliczeń dla każdego przebiegu. Jeśli używasz tego samego wystąpienia do uruchomienia innej operacji, agreguje nowe wyniki z istniejącymi wynikami. Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego przebiegu.

### <a name="invoking-the-resources-estimator-from-python"></a>Wywoływanie zasobów szacowania z języka Python

Użyj metody [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną Q# operacją:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Wywoływanie zasobów szacowania z wiersza polecenia

Podczas uruchamiania Q# programu z wiersza polecenia należy użyć parametru **--symulatora** (lub **-s** ), aby określić `ResourcesEstimator` maszynę docelową. Następujące polecenie uruchamia program przy użyciu szacowania zasobów: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Wywoływanie zasobów szacowania z notesów Juptyer

Q#Aby uruchomić operację, użyj polecenia I [oszacowania% oszacowanie](xref:microsoft.quantum.iqsharp.magic-ref.simulate) Q# .

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Programowe pobieranie szacowanych danych

Oprócz tabeli TSV można programowo pobrać zasoby szacowane podczas wykonywania przez `Data` Właściwość zasobów szacowania. `Data`Właściwość zawiera `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.

Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` operacji oraz operacje wykonywane przez Q# operację:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Zgłoszone metryki

Szacowania zasobów śledzi następujące metryki:

|Metryka|Opis|
|----|----|
|__CNOT__    |Liczba uruchomień `CNOT` operacji (znanych także jako kontrolowane operacje Pauli X).|
|__QubitClifford__ |Liczba uruchomień pojedynczego qubit Clifford i Pauli operacji.|
|__Measure__    |Liczba uruchomień pomiarów.  |
|__R__    |Liczba uruchomień wszystkich rotacji qubit, z wyjątkiem `T` operacji Clifford i Pauli.  |
|__T__    |Liczba uruchomień `T` operacji i ich sprzężenia, w tym `T` operacje, T_x = H. T. H i T_y = HY. T. HY.  |
|__Ścisł__|Głębokość obwodu Quantum uruchamianego przez Q# operację (patrz [poniżej](#depth-width-and-qubitcount)). Domyślnie Metryka głębokości liczy tylko `T` bramy. Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__|Szerokość obwodu Quantum uruchamianego przez Q# operację (patrz [poniżej](#depth-width-and-qubitcount)). Domyślnie Metryka głębokości liczy tylko `T` bramy. Aby uzyskać więcej informacji, zobacz [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |Dolna granica maksymalnej liczby qubits przydzieloną podczas uruchamiania Q# operacji. Ta Metryka może nie być zgodna z __głębokością__ (patrz poniżej).  |
|__BorrowedWidth__    |Maksymalna liczba qubits zaciągniętych w ramach Q# operacji.  |


## <a name="depth-width-and-qubitcount"></a>Głębokość, Szerokość i QubitCount

Raportowane oszacowania głębokości i szerokości są zgodne ze sobą.
(Poprzednio obie liczby były osiągalne, ale na potrzeby głębokości i szerokości są wymagane różne obwody.) Obecnie obie metryki w tej parze mogą być osiągane przez ten sam obwód w tym samym czasie.

Zgłaszane są następujące metryki:

__Głębokość:__ W przypadku operacji głównej należy wykonać ją w celu jej wykonania przy założeniu określonych czasów bramy.
Dla operacji o nazwie lub późniejszych wartościach czasowych między najnowszym czasem dostępności qubit na początku i na końcu operacji.

__Szerokość:__ W przypadku operacji głównej — liczba qubits rzeczywiście użyta do jej wykonania (i operacji wywoływanych przez nią).
W przypadku operacji o wartościach lub kolejnych operacjach — ile więcej qubits było używanych oprócz qubits już używanych na początku operacji.

Należy pamiętać, że ponownie użyte qubits nie przyczyniają się do tej liczby.
Oznacza to, że jeśli kilka qubits zostało zwolnionych przed rozpoczęciem operacji i wszystkie qubit wymagane przez tę operację a (i operacje wywoływane z) zostały spełnione przez ponowne użycie poprzednio wydanej wersji qubits, Szerokość operacji A jest raportowana jako 0. Pomyślnie pożyczone qubits nie przyczyniają się do szerokości.

__QubitCount:__ W przypadku operacji głównej — minimalna liczba qubits, które byłyby wystarczające do wykonania tej operacji (i wywoływanej z niej operacji).
W przypadku operacji o nazwie lub kolejnych operacji — minimalna liczba qubits, które byłyby wystarczające do wykonania tej operacji osobno. Ta liczba nie zawiera qubits danych wejściowych. Obejmuje to zapożyczone qubits.

Obsługiwane są dwa tryby operacji. Tryb jest wybierany przez ustawienie QCTraceSimulatorConfiguration. OptimizeDepth.

__OptimizeDepth = true:__ Nie zaleca się QubitManager z qubit ponownie i przydziela nowe qubit za każdym razem, gdy zostanie wyświetlony monit o qubit. Dla __głębokości__ operacji głównej jest to minimalna głębokość (Dolna granica). Dla tej głębokości zgłoszono zgodną __Szerokość__ (obie można osiągnąć w tym samym czasie). Należy zauważyć, że ta szerokość prawdopodobnie nie będzie optymalna. Wartość __QubitCount__ może być mniejsza niż szerokość operacji głównej, ponieważ zakłada się jej ponowne użycie.

__OptimizeDepth = FAŁSZ:__ QubitManager zaleca się ponowne użycie qubits i ponowne użycie zwolnienia qubits przed przydzieleniem nowych. __Szerokość__ operacji głównej jest minimalna (Dolna granica). Jest raportowana zgodna __głębokość__ , na której można ją osiągnąć. __QubitCount__ będzie taka sama jak __Szerokość__ dla operacji głównej, przy założeniu, że nie pożyczy się.

## <a name="providing-the-probability-of-measurement-outcomes"></a>Podawanie prawdopodobieństwa wyników pomiarów

Możesz użyć <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw, aby podać informacje o oczekiwanym prawdopodobieństwie operacji pomiaru. Aby uzyskać więcej informacji, zobacz [symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Zobacz także

- [Symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Kwantowy symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kwantowy symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator) 
