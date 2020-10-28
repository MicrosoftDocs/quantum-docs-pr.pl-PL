---
title: Słownik biblioteki Quantum Machine Learning
description: Słownik terminów dotyczących programu Quantum Machine Learning
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 476e93e3737dee6ad8f3a97e8ffbcfb9b0012ee1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691519"
---
# <a name="quantum-machine-learning-glossary"></a>Słownik Quantum Machine Learning

Uczenie klasyfikatora opartego na obwodach jest procesem z wieloma ruchomymi częściami, które wymagają tego samego (lub nieco większego) stopnia kalibracji w okresie próbnym i błędów jako szkolenia tradycyjnych klasyfikatorów. Tutaj definiujemy główne koncepcje i składniki tego procesu szkoleniowego.

## <a name="trainingtesting-schedules"></a>Harmonogramy szkoleń/testów

W kontekście szkolenia klasyfikatora *harmonogram* zawiera opis podzestawu próbek danych w ramach ogólnego szkolenia lub zestawu testów. Harmonogram jest zwykle definiowany jako kolekcja przykładowych indeksów.

## <a name="parameterbias-scores"></a>Wyniki parametru/Bias

W przypadku wektora parametrów kandydujących i odchylenia klasyfikatora ich *wyniki sprawdzania poprawności* są mierzone względem wybranego harmonogramu walidacji i są wyrażane przez wiele nieprawidłowych klasyfikacji na wszystkich przykładach w harmonogramie s.

## <a name="hyperparameters"></a>Hiperparametry

Proces szkolenia modelu podlega określonym wstępnie określonym wartościom, które są nazywane *parametrami* :

### <a name="learning-rate"></a>Tempo nauki

Jest to jeden z najważniejszych parametrów. Definiuje, ile bieżącego oszacowania gradientu stochastycznego ma wpływ na aktualizację parametru. Rozmiar różnic między aktualizacjami parametrów jest proporcjonalny do stawki szkoleniowej. Mniejsze wartości szybkości uczenia prowadzą do wolniejszego ewolucji parametrów i wolniejszych zbieżności, ale nadmiernie duże wartości LR mogą spowodować przerwanie zbieżności, gdy gradient nie jest nigdy zatwierdzany do określonego minimum lokalnego. Częstotliwość uczenia jest dostosowywana do pewnego stopnia przez algorytm szkoleniowy, dlatego należy wybrać dobrą wartość początkową. Normalna wartość domyślna dla stawki szkoleniowej to 0,1. Wybór najlepszej wartości stawki szkoleniowej to świetna część (patrz na przykład sekcja 4,3 of Goodfellow et al., "Uczenie głębokie", MIT, 2017).

### <a name="minibatch-size"></a>Rozmiar Minibatch

Definiuje liczbę próbek danych używanych do pojedynczego oszacowania gradientu stochastycznego. Większe wartości rozmiaru minibatch zazwyczaj prowadzą do bardziej niezawodnej i większej spójności monotoniczny, ale mogą spowodować spowolnienie procesu szkolenia, ponieważ koszt dowolnego oszacowania gradientu jest proporcjonalny do rozmiaru minimatch. Normalna wartość domyślna dla rozmiaru minibatch wynosi 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Treningi, tolerancja, gridlocks

"Epoka" oznacza jedno kompletne przejście przez zaplanowane dane szkoleniowe.
Maksymalna liczba epok na wątek szkoleniowy (patrz poniżej) powinna być ograniczona. Wątek szkoleniowy jest zdefiniowany do zakończenia (z najlepszymi znanymi parametrami kandydatów), gdy została uruchomiona Maksymalna liczba epok. Jednak takie szkolenie zostanie zakończone wcześniej, gdy wartość w harmonogramie sprawdzania poprawności nie będzie mniejsza niż wybrana tolerancja. Załóżmy na przykład, że niedozwolona tolerancja klasyfikacji wynosi 0,01 (1%); Jeśli na 2000 zestawie walidacji próbek jest wyświetlana mniej niż 20 błędów klasyfikacji, osiągnięto poziom tolerancji. Wątek szkoleniowy kończy się również przedwcześnie, jeśli wynik sprawdzania poprawności modelu kandydata nie pokazał żadnych ulepszeń w przypadku kilku kolejnych epok (korków). Logika dla zakończenia korków jest obecnie stałe.

### <a name="measurements-count"></a>Liczba pomiarów

Oszacowanie wyników szkolenia/sprawdzania poprawności oraz składników gradientu stochastycznego na urządzeniu Quantum powoduje oszacowanie nakładających się Stanów Quantum, które wymagają wielu pomiarów odpowiednich observables. Liczba pomiarów powinna być skalowana jako $O (1/\ Epsilon ^ 2) $, gdzie $ \epsilon $ to żądany błąd szacowania.
Jako zasada elementu kciuk liczba początkowych pomiarów może wynosić około $1/\ mbox {tolerancja} ^ 2 $ (Zobacz definicję tolerancji w poprzednim akapicie). Musimy skorygować liczbę pomiarów w górę, jeśli wyświetlona wartość gradientu wydaje się zbyt nieprawidłowa i zbieżność jest zbyt trudna do osiągnięcia.

### <a name="training-threads"></a>Wątki szkoleniowe

Funkcja prawdopodobieństwa, która jest narzędziem szkoleniowym klasyfikatora, jest bardzo rzadko wypukła, co oznacza, że zwykle ma wiele Optima lokalnych w przestrzeni parametrów, które mogą się różnić w zależności od jakości. Ponieważ proces SGD może być zbieżny tylko z jednym określonym optymalnie, ważne jest, aby poznać wiele wektorów parametrów początkowych. Typowym sposobem uczenia maszynowego jest zainicjowanie takich wektorów uruchamiania losowo. Q#Interfejs API uczenia akceptuje dowolną tablicę takich wektorów, ale kod źródłowy eksploruje je sekwencyjnie. Na komputerze z wieloma rdzeniami lub w przypadku dowolnej architektury obliczeń równoległych zaleca się wykonanie kilku wywołań Q# interfejsu API szkolenia równolegle z innymi inicjalizacjami parametrów dla wywołań.

#### <a name="how-to-modify-the-hyperparameters"></a>Jak zmodyfikować parametry

W bibliotece QML najlepszym sposobem modyfikowania parametrów jest zastępowanie wartości domyślnych UDT [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) . W tym celu należy wywołać tę funkcję [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) i zastosować operator `w/` w celu zastąpienia wartości domyślnych. Na przykład, aby użyć 100 000 pomiarów i szybkość uczenia 0,01:

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
