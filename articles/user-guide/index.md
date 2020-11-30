---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231761"
---
# <a name="the-no-locq-user-guide"></a>Podręcznik użytkownika języka Q#

Podręcznik użytkownika języka Q# — Zapraszamy! 

W różnych tematach tego przewodnika wprowadzamy podstawowe informacje na temat tworzenia programów kwantowych za pomocą języka Q#.

Odwołujemy się do [podręcznika języka Q#](xref:microsoft.quantum.qsharp.index), który zawiera pełną specyfikację i dokumentację kwantowego języka programowania Q#. 

## <a name="user-guide-contents"></a>Zawartość podręcznika użytkownika

- [Programy w języku Q#](xref:microsoft.quantum.guide.programs): Krótkie wprowadzenie do programów kwantowych w języku Q#. 

- [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs): Zawiera opis sposobu uruchamiania programu w języku Q# i udostępnia przegląd różnych metod wywoływania programu: z wiersza polecenia, w notesach Jupyter Notebook języka Q# lub z klasycznego programu hosta napisanego w języku Python lub języku platformy .NET.

- [Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): Szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami. 
    Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik. 
    Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, które są znane programistom, a także tych, które są specyficzne dla programów kwantowych. Obejmuje to tworzenie i uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stany maszyn docelowych. 
    Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. [twierdzenia o braku klonowania](xref:microsoft.quantum.concepts.pauli)).

### <a name="quantum-simulators-and-resource-estimators"></a>Symulatory kwantowe i narzędzia do szacowania zasobów

- [Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): Omówienie różnych dostępnych symulatorów oraz tego, jak programy hosta i maszyny docelowe współdziałają w celu uruchamiania programów Q#.

- [Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): Maszyna docelowa, która symuluje pełny stan kwantowy. Przydatne do pełnego uruchamiania lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)

- [Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): Szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.

- [Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Umożliwia uruchamianie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może uruchamiać programy kwantowe korzystające z tysięcy kubitów. Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.

- [Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): Symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (X, CNOT i kontrolowanych wielokrotnie operacji X).

### <a name="quick-reference-pages"></a>Strony skróconej dokumentacji

- [Polecenia magic rozszerzenia IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic rozszerzenia IQ# w ramach notesów Jupyter Notebook dla języka Q#.
