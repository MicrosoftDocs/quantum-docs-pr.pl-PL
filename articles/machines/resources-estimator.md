---
title: Szacowania zasobów zestawu Quantum Development Kit
description: 'Dowiedz się więcej o zasobach szacowania, które szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 01d242ed405bdd326f65e534f82ff378a464ee7d
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426876"
---
# <a name="the-resources-estimator-target-machine"></a>Maszyna docelowa szacowania zasobów

Jako że nazwa oznacza, `ResourcesEstimator` szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q # na komputerze z systemem Quantum.
Jest to realizowane przez wykonywanie operacji Quantum bez faktycznego symulowania stanu komputera Quantum; z tego powodu można oszacować zasoby dla operacji Q #, które używają tysięcy qubits, jeśli klasyczna część kodu może być uruchamiana w rozsądnym czasie.

## <a name="usage"></a>Sposób użycia

`ResourcesEstimator`Jest to tylko inny typ maszyny docelowej, dlatego może służyć do uruchamiania dowolnej operacji Q #. 

Innymi maszynami docelowymi, aby użyć ich w programie hosta C# i utworzyć wystąpienie i przekazać je jako pierwszy parametr `Run` metody operacji:

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

Jak pokazano w przykładzie, `ResourcesEstimator` zapewnia `ToTSV()` metodę generowania tabeli z wartościami rozdzielanymi znakami tabulacji (tsv), które można zapisać w pliku lub zapisywanych w konsoli na potrzeby analizy. Dane wyjściowe powyższego programu powinny wyglądać następująco:

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
> Nie `ResourcesEstimator` resetuje obliczeń dla każdego przebiegu, jeśli to samo wystąpienie jest używane do wykonania kolejnej operacji, spowoduje to zachowanie agregowania liczników na podstawie istniejących wyników.
> Jeśli musisz zresetować obliczenia między przebiegami, Utwórz nowe wystąpienie dla każdego wykonania.


## <a name="programmatically-retrieving-the-estimated-data"></a>Programowe pobieranie szacowanych danych

Oprócz tabeli TSV, szacowane zasoby mogą być pobierane programowo za pośrednictwem `ResourcesEstimator` `Data` właściwości. `Data`oferuje `System.DataTable` wystąpienie z dwiema kolumnami: `Metric` i `Sum` , indeksowane przez nazwy metryk.

Poniższy kod pokazuje, jak pobrać i wydrukować łączną liczbę `QubitClifford` `T` `CNOT` bram używanych przez operację Q #:

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

Poniżej znajduje się lista metryk szacowanych przez `ResourcesEstimator` :

* __CNOT__: liczba wykonanych bram CNOT (znanych także jako kontrolowane bramy Pauli X).
* __QubitClifford__: liczba wykonanych pojedynczej bramy qubit Clifford i Pauli.
* __Miara__: liczba wykonanych pomiarów.
* __R__: liczba wykonanych pojedynczych rotacji qubit, z wyjątkiem bram T, Clifford i Pauli.
* __T__: liczba bram t i ich sprzężenia, łącznie z bramą t, T_x = H. T. H i T_y = HY. t. HY, wykonane.
* __Głębokość__: Głębokość obwodu Quantum wykonywanego przez operację Q #. Domyślnie tylko bramy T są zliczane na głębokości, szczegóły można znaleźć w temacie [głębokość licznika](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: Maksymalna liczba qubits przypisana podczas wykonywania operacji Q #.
* __BorrowedWidth__: Maksymalna liczba qubits została zapożyczone w ramach operacji Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Podawanie prawdopodobieństwa wyników pomiarów

<xref:microsoft.quantum.intrinsic.assertprob>z <xref:microsoft.quantum.intrinsic> przestrzeni nazw można korzystać w celu podania informacji o oczekiwanym prawdopodobieństwie pomiaru, aby ułatwić wykonanie programu Q #. Zostało to przedstawione w poniższym przykładzie:

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

Gdy `ResourcesEstimator` napotkają, `AssertProb` nastąpi zapisanie tego, że pomiar jest `PauliZ` włączony `source` i `q` powinien zostać uzyskany wynik `Zero` prawdopodobieństwa 0,5. Gdy zostanie on wykonany `M` później, znajdzie zarejestrowane wartości prawdopodobieństwa wyniku i `M` zwróci `Zero` lub `One` z prawdopodobieństwem 0,5.


## <a name="see-also"></a>Zobacz też

`ResourcesEstimator`Jest zbudowany na podstawie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum, który zapewnia bogatszy zestaw metryk, możliwość zgłaszania metryk w całym grafie wywołań i funkcji, takich jak [różne dane wejściowe](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , aby pomóc w znalezieniu usterek w programach Q #. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją dotyczącą [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

