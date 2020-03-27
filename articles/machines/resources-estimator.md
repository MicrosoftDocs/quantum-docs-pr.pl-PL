---
title: Szacowania zasobów zestawu Quantum Development Kit
description: 'Dowiedz się więcej o zasobach szacowania, które szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 51186134e9279727fec212cdce84f69493aaa656
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320808"
---
# <a name="the-resourcesestimator-target-machine"></a>Maszyna docelowa ResourcesEstimator

Jak nazywa się, `ResourcesEstimator` szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze Quantum.
Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu można oszacować zasoby dla operacji Q #, które używają tysięcy qubits, jeśli klasyczna część kodu może być uruchamiana w rozsądnym czasie.

## <a name="usage"></a>Sposób użycia

`ResourcesEstimator` jest tylko innym typem maszyny docelowej, dlatego może służyć do uruchamiania dowolnej operacji Q #. 

W przypadku innych maszyn docelowych, aby użyć jej w C# programie hosta, Utwórz wystąpienie i przekaż je jako pierwszy parametr metody `Run` operacji:

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

Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia metodę `ToTSV()`, aby wygenerować tabelę z wartościami rozdzielanymi znakami tabulacji (TSV), które można zapisać w pliku lub zapisać w konsoli programu w celu przeprowadzenia analizy. Dane wyjściowe powyższego programu powinny wyglądać następująco:

```Output
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
> `ResourcesEstimator` nie resetuje obliczeń dla każdego przebiegu, jeśli to samo wystąpienie jest używane do wykonania kolejnej operacji, spowoduje to zachowywanie liczby agregowania na podstawie istniejących wyników.
> Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego wykonania.


## <a name="programmatically-retrieving-the-estimated-data"></a>Programowe pobieranie szacowanych danych

Oprócz tabeli TSV, szacowane zasoby mogą być pobierane programowo za pośrednictwem właściwości `Data` `ResourcesEstimator`. `Data` udostępnia wystąpienie `System.DataTable` z dwiema kolumnami: `Metric` i `Sum`, indeksowane przez nazwy metryk.

Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford`, `T` i `CNOT` bram używanych przez operację Q #:

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

Poniżej znajduje się lista metryk szacowanych przez `ResourcesEstimator`:

* __CNOT__: liczba wykonanych bram CNOT (znanych także jako kontrolowane bramy Pauli X).
* __QubitClifford__: liczba wykonanych pojedynczej bramy qubit Clifford i Pauli.
* __Miara__: liczba wykonanych pomiarów.
* __R__: liczba wykonanych pojedynczych rotacji qubit, z wyjątkiem bram T, Clifford i Pauli.
* __T__: liczba bram t i ich sprzężenia, łącznie z bramą t, T_x = H. T. H i T_y = HY. t. HY, wykonane.
* __Głębokość__: Głębokość obwodu Quantum wykonywanego przez operację Q #. Domyślnie tylko bramy T są zliczane na głębokości, szczegóły można znaleźć w temacie [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: Maksymalna liczba qubits przypisana podczas wykonywania operacji Q #.
* __BorrowedWidth__: Maksymalna liczba qubits została zapożyczone w ramach operacji Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Podawanie prawdopodobieństwa wyników pomiarów

<xref:microsoft.quantum.intrinsic.assertprob> z przestrzeni nazw <xref:microsoft.quantum.intrinsic> można użyć, aby podać informacje o oczekiwanym prawdopodobieństwie pomiaru, aby ułatwić wykonanie programu Q #. Zostało to przedstawione w poniższym przykładzie:

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

Gdy `ResourcesEstimator` napotka `AssertProb`, nastąpi zapisanie `PauliZ` pomiaru na `source` i `q` należy otrzymać wynik `Zero` z prawdopodobieństwem 0,5. Gdy zostanie on wykonany `M` później, będzie znajdował zarejestrowane wartości prawdopodobieństwa wyniku i `M` zwróci `Zero` lub `One` z prawdopodobieństwem 0,5.


## <a name="see-also"></a>Zobacz też

`ResourcesEstimator` jest tworzona na podstawie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum, który zapewnia bogatszy zestaw metryk, możliwość raportowania metryk w pełnym wywołaniu grafu i funkcji, takich jak [odrębne dane wejściowe](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , aby ułatwić znajdowanie usterek w programach Q #. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją dotyczącą [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

