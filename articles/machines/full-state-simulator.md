---
title: Symulator pełnego stanu zestawu Quantum Development Kit | Microsoft Docs
description: Omówienie symulatora pełnego stanu zestawu Quantum Development Kit firmy Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184682"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Symulator trybu pełnego stanu zestawu Quantum Development Kit

Zestaw Quantum Development Kit zawiera pełny stan symulatora Quantum podobny do [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) from Microsoft Research.
Ten symulator może służyć do wykonywania i debugowania algorytmów Quantum, które są zapisywane w Q # na komputerze.

Ten symulator Quantum jest udostępniany za pośrednictwem klasy `QuantumSimulator`. Aby użyć symulatora, wystarczy utworzyć wystąpienie tej klasy i przekazać je do metody `Run` operacji Quantum, która ma zostać wykonana wraz z resztą parametrów:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

Klasa `QuantumSimulator` implementuje <xref:System.IDisposable>, dlatego Metoda `Dispose` powinna być wywoływana, gdy wystąpienie symulatora nie jest już używane. Najlepszym sposobem jest otoczenie symulatora w instrukcji `using`, jak w powyższym przykładzie.

## <a name="seed"></a>Sadzenia

`QuantumSimulator` używa generatora liczb losowych w celu symulowania losowości Quantum. W celach testowych czasami warto mieć deterministyczne wyniki. Można to osiągnąć przez udostępnienie inicjatora dla generatora liczb losowych w konstruktorze `QuantumSimulator`za pośrednictwem parametru `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Wątk

`QuantumSimulator` używa [OpenMP](http://www.openmp.org/) do zrównoleglanie algebry liniowy. Domyślnie OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą qubits często działają wolniej, ponieważ wymagana jest koordynacja Dwarf rzeczywistej pracy. Można to naprawić przez ustawienie zmiennej środowiskowej `OMP_NUM_THREADS` na małą liczbę. Bardzo niewielką zasadą jest, że 1 wątek jest dobry dla maksymalnie 4 qubits, a następnie dodatkowy wątek na qubit jest dobry, chociaż jest to wysoce zależny od algorytmu.

