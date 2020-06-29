---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: c5611f3e2907791f2dfc1644be0a45515d50dfd7
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415372"
---
# <a name="the-q-user-guide"></a>Podręcznik użytkownika języka Q#

Podręcznik użytkownika języka Q# — Zapraszamy! 

W poszczególnych tematach tego przewodnika opisano szczegółowo podstawowe pojęcia dotyczące języka Q# oraz wszystkie informacje potrzebne do pisania programów kwantowych.

## <a name="user-guide-contents"></a>Zawartość podręcznika użytkownika

- [Podstawy języka Q#](xref:microsoft.quantum.guide.basics): Wprowadzające omówienie dotyczące przeznaczenia i funkcjonalności języka programowania Q#. 

### <a name="q-language"></a>Język Q#

- [Typy w języku Q#](xref:microsoft.quantum.guide.types): Opis modelu typów języka Q# oraz składni służącej do określania typów i pracy z nimi.

- [Wyrażenia typów](xref:microsoft.quantum.guide.expressions): Szczegóły dotyczące określania, odwoływania się, łączenia i wykonywania operacji w przypadku wartości poszczególnych typów w języku Q#. 

### <a name="using-q"></a>Korzystanie z języka Q#

- [Struktura plików języka Q#](xref:microsoft.quantum.guide.filestructure): Opis struktury i składni pliku języka Q# `*.qs`.

- [Operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions): Szczegóły dwóch wywoływalnych typów w języku Q#: *operacji*, które obejmują akcje dotyczące rejestrów kubitów, oraz *funkcji*, które współpracują wyłącznie z informacjami klasycznymi. 
    W tym miejscu opisano, jak je definiować i wywoływać, łącznie ze sprzężonymi i kontrolowanymi wersjami operacji kwantowych.

- [Zmienne](xref:microsoft.quantum.guide.variables): Opis roli zmiennych w programach języka Q# oraz sposobu ich skutecznego używania. 
    Na przykład dostępne są informacje o zakresach powiązań, różnicach między zmiennymi, których nie można modyfikować, i tymi, które można modyfikować, a także o sposobie ich przypisywania i ponownego przypisywania.

- [Praca z kubitami](xref:microsoft.quantum.guide.qubits): Opis funkcji języka Q# używanych do adresowania poszczególnych kubitów i systemów kubitów, w szczególności do alokowania ich, wykonywania operacji na nich i mierzenia ich. 

- [Przepływ sterowania](xref:microsoft.quantum.guide.controlflow): Szczegóły programowania wzorców przepływu sterowania dostępnych w języku Q#, które obejmują wiele standardowych technik (wykonywanie warunkowe, pętle for, pętle while itp.), a także wzorzec specyficzny dla programów kwantowych „Repeat-Until-Success”.

- [Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): Szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami. 
    Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik. 
    Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, które są znane programistom, a także tych, które są specyficzne dla programów kwantowych. Obejmuje to tworzenie i uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stan maszyn docelowych. 
    Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. [twierdzenia o braku klonowania](xref:microsoft.quantum.concepts.pauli)).

### <a name="quantum-simulators-and-resource-estimators"></a>Symulatory kwantowe i narzędzia do szacowania zasobów

- [Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): Omówienie różnych dostępnych symulatorów oraz ogólnego modelu wykonywania między programami hosta a maszynami docelowymi.

- [Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): Maszyna docelowa, która symuluje pełny stan kwantowy. Przydatne do pełnego uruchomienia lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)

- [Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): Szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.

- [Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może wykonywać programy kwantowe korzystające z tysięcy kubitów. Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.

- [Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): Symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (X, CNOT i kontrolowanych wielokrotnie operacji X).

### <a name="quick-reference-pages"></a>Strony skróconej dokumentacji

- [Polecenia magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic IQ# w ramach notesów Jupyter dla języka Q#.
