---
title: Symulator stanu pełnego
description: 'Dowiedz się, jak uruchamiać programy Q # na Microsoft Quantum Development Kit symulatorze pełnego stanu.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275642"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Symulator trybu pełnego stanu zestawu Quantum Development Kit

Zestaw Quantum Development Kit zawiera pełny stan symulatora Quantum podobny do [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) from Microsoft Research.
Ten symulator może służyć do wykonywania i debugowania algorytmów Quantum, które są zapisywane w Q # na komputerze.

Ten symulator Quantum jest udostępniany za pośrednictwem `QuantumSimulator` klasy. Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do `Run` metody operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator`Klasa implementuje <xref:System.IDisposable> , dlatego `Dispose` Metoda powinna być wywoływana, gdy wystąpienie symulatora nie jest już używane. Najlepszym sposobem jest otoczenie symulatora w `using` instrukcji, jak w powyższym przykładzie.

## <a name="seed"></a>Sadzenia

`QuantumSimulator`Używa generatora liczb losowych do symulowania losowości Quantum. W celach testowych czasami warto mieć deterministyczne wyniki. Można to osiągnąć, dostarczając inicjator dla generatora liczb losowych w `QuantumSimulator` konstruktorze za pośrednictwem `randomNumberGeneratorSeed` parametru:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Wątki

`QuantumSimulator`Użycie [OpenMP](http://www.openmp.org/) zrównoleglanie algebry liniowy. Domyślnie interfejs OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą kubitów często działają wolniej, ponieważ wymóg koordynacji powoduje spowolnienie rzeczywistej pracy. Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę. Można kierować się zasadą, że w przybliżeniu 1 wątek jest wystarczający dla około 4 kubitów. Następnie na jeden kubit powinien przypadać jeden dodatkowy wątek. Jest to jednak szacowanie wysoce zależne od konkretnego algorytmu.

