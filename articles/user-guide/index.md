---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430615"
---
# <a name="the-q-user-guide"></a>Podręcznik użytkownika języka Q#

Podręcznik użytkownika języka Q# — Zapraszamy! 

Opisano tutaj szczegółowo podstawowe pojęcia dotyczące języka Q# oraz wszystkie informacje potrzebne do pisania programów kwantowych.

## <a name="user-guide-contents"></a>Zawartość podręcznika użytkownika

- [Podstawy języka Q# ](xref:microsoft.quantum.guide.basics): omówienie wprowadzające dotyczące przeznaczenia i funkcjonalności języka programowania Q#. 

### <a name="q-language"></a>Język Q#

- [Typy w języku Q#](xref:microsoft.quantum.guide.types): sekcja określa model typu języka Q# i opisuje składnię służącą do określania typów i pracy z nimi.

- [Wyrażenia typu](xref:microsoft.quantum.guide.expressions): w sekcji znajdują się szczegóły dotyczące określania, odwoływania, łączenia i wykonywania operacji na wartościach każdego typu w języku Q#. 

### <a name="using-q"></a>Korzystanie z języka Q#

- [Struktura plików języka Q#](xref:microsoft.quantum.guide.filestructure): w tej sekcji opisano strukturę i składnię pliku języka Q# `*.qs`.

- [Operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions): sekcja zawiera szczegóły dwóch wywoływalnych typów w języku Q#: *operacji*, które obejmują akcje względem rejestrów kubitów oraz *funkcji*, które współpracują wyłącznie z informacjami klasycznymi. 
    W tym miejscu opisano, jak je definiować i wywoływać, łącznie ze sprzężonymi i kontrolowanymi wersjami operacji kwantowych.

- [Zmienne lokalne](xref:microsoft.quantum.guide.variables): sekcja opisuje rolę zmiennych w programach w języku Q# oraz sposób ich skutecznego używania. 
    Na przykład można znaleźć informacje na temat zakresów powiązań, a także różnice między zmiennymi, których nie można modyfikować, i tymi, które można modyfikować, oraz dowiesz się, jak je przypisywać i przypisywać ponownie.

- [Praca z kubitami](xref:microsoft.quantum.guide.qubits): sekcja zawiera opis funkcji języka Q# używanych do obsługi pojedynczych kubitów i systemów kubitów. 
    W szczególności oznacza to ich alokację, wykonywanie na nich operacji oraz, ostatecznie, ich pomiar. 

- [Przepływ sterowania](xref:microsoft.quantum.guide.controlflow): sekcja zawiera szczegóły programowania wzorców przepływu sterowania dostępne w języku Q#, które obejmują wiele standardowych technik (wykonywanie warunkowe, pętle for, pętle while itp.), a także wzorzec specyficzny dla programów kwantowych „Repeat-Until-Success”.

- [Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): w sekcji opisano szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami. 
    Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik. 
    Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, do których programiści są przyzwyczajeni, a także tych, które są specyficzne dla programów kwantowych. Obejmuje to tworzenie/uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stan maszyny docelowej. 
    Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. twierdzenia o braku klonowania).

### <a name="quantum-simulators-and-resource-estimators"></a>Symulatory kwantowe i narzędzia do szacowania zasobów

- [Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): sekcja zawiera przegląd różnych dostępnych symulatorów, a także ogólny model wykonywania między programem hosta a maszynami docelowymi.

- [Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): maszyna docelowa, która symuluje pełny stan kwantowy. Przydatne do pełnego uruchomienia lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)

- [Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.

- [Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może wykonywać programy kwantowe korzystające z tysięcy kubitów. Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.

- [Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (mianowicie X, CNOT i kontrolowanych wielokrotnie operacji X).

### <a name="quick-reference-pages"></a>Strony skróconej dokumentacji

- [Polecenia magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic IQ# w ramach notesów Jupyter dla języka Q#.
