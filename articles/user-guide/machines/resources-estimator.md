---
title: Zasoby Quantum szacowania-Quantum Development Kit
description: 'Dowiedz się więcej o programie Microsoft QDKe szacowania, który szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870548"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Zasoby zestawu Quantum Development Kit (QDK) szacowania

Jak nazywa się, `ResourcesEstimator` Klasa szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze Quantum. Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu szacuje zasoby dla operacji Q #, które używają tysięcy qubits, pod warunkiem, że klasyczna część kodu jest uruchamiana w rozsądnym czasie.

Szacowania zasobów jest oparty na [symulatorze śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), który zapewnia bogatszy zestaw metryk i narzędzi ułatwiających debugowanie programów Q #.

## <a name="invoking-and-running-the-resources-estimator"></a>Wywoływanie i uruchamianie zasobów szacowania

Możesz użyć szacowania zasobów do uruchomienia dowolnej operacji Q #. Aby uzyskać dodatkowe informacje, zobacz [sposoby uruchamiania programu Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Wywoływanie zasobów szacowania z języka C # 

Podobnie jak w przypadku innych komputerów docelowych, należy najpierw utworzyć wystąpienie `ResourceEstimator` klasy, a następnie przekazać je jako pierwszy parametr `Run` metody operacji.

Należy pamiętać, że w przeciwieństwie do `QuantumSimulator` klasy `ResourceEstimator` Klasa nie implementuje <xref:System.IDisposable> interfejsu, dlatego nie trzeba go umieszczać w `using` instrukcji.

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

Użyj metody [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z biblioteki języka Python z zaimportowaną operacją Q #:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Wywoływanie zasobów szacowania z wiersza polecenia

Podczas uruchamiania programu Q # z wiersza polecenia, użyj parametru **--symulatora** (lub **-s** skrótu), aby określić `ResourcesEstimator` maszynę docelową. Następujące polecenie uruchamia program przy użyciu szacowania zasobów: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Wywoływanie zasobów szacowania z notesów Juptyer

Użyj polecenia IQ # Magic [% oszacowanie](xref:microsoft.quantum.iqsharp.magic-ref.simulate) , aby uruchomić operację Q #.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Programowe pobieranie szacowanych danych

Oprócz tabeli TSV można programowo pobrać zasoby szacowane podczas wykonywania przez `Data` Właściwość zasobów szacowania. `Data`Właściwość zawiera `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.

Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` operacji oraz operacje używane przez operację Q #:

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
|__miara__    |Liczba uruchomień pomiarów.  |
|__R__    |Liczba uruchomień wszystkich rotacji qubit, z wyjątkiem `T` operacji Clifford i Pauli.  |
|__T__    |Liczba uruchomień `T` operacji i ich sprzężenia, w tym `T` operacje, T_x = H. T. H i T_y = HY. T. HY.  |
|__Ścisł__|Dolna granica głębokości obwodu Quantum przebiegu przez operację Q #. Domyślnie Metryka głębokości liczy tylko `T` bramy. Aby uzyskać więcej informacji, zobacz [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__    |Dolna granica maksymalnej liczby qubits przydzieloną podczas przebiegu operacji Q #. Jednocześnie może nie być możliwe równoczesne osiąganie __głębokości__ i dolnej granicy __szerokości__ .  |
|__BorrowedWidth__    |Maksymalna liczba qubits zaciągniętych w ramach operacji Q #.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Zapewnianie prawdopodobieństwa wyników pomiarów

Możesz użyć <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> przestrzeni nazw, aby podać informacje o oczekiwanym prawdopodobieństwie operacji pomiaru. Aby uzyskać więcej informacji, zobacz [symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Zobacz także

- [Symulator śledzenia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Symulator Toffoli Quantum](xref:microsoft.quantum.machines.toffoli-simulator)
- [Symulator pełnego stanu Quantum](xref:microsoft.quantum.machines.full-state-simulator) 