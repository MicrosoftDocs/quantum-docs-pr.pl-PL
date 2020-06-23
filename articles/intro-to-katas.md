---
title: Wprowadzenie do artykułów Quantum Kata
description: Dowiedz się więcej o ćwiczeniach szkoleniowych kata dostarczanych z zestawem Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 0731f47061163e5317d026b2b118e9d39048227d
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578121"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Nauka wykonywania obliczeń kwantowych z artykułów Quantum Kata

[Quantum Kata](https://github.com/Microsoft/QuantumKatas/) to seria realizowanych samodzielnie samouczków i ćwiczeń programistycznych typu open-source, które służą zarówno do nauki elementów obliczeń kwantowych, jak i programowania w języku Q#.

## <a name="learning-by-doing"></a>Nauka przez praktykę

W samouczkach i ćwiczeniach zebranych w tym projekcie położono nacisk na uczenie się przez praktykę: udostępniają one zadania programistyczne obejmujące różne tematy, od bardzo prostych do stosunkowo trudnych. Każde zadanie wymaga wypełnienia kodu. Pierwsze zadania mogą wymagać tylko jednego wiersza, a następne mogą wymagać dużego fragmentu kodu.

Co najważniejsze, artykuły Kata obejmują struktury testowe, które konfigurują, uruchamiają i weryfikują rozwiązania zadań. Dzięki temu możesz szybko uzyskiwać informacje zwrotne na temat swojego rozwiązania i ponownie rozważać swoje podejście, jeśli jest ono nieprawidłowe.

Możesz używać artykułów kata do uczenia się w wybranym środowisku:

* Notesy Jupyter online w środowisku integratora
* Notesy Jupyter uruchomione na komputerze lokalnym
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Czego można się nauczyć z artykułów Quantum Kata?

Poznaj podstawy obliczeń kwantowych lub bardziej zaawansowane algorytmy i protokoły kwantowe. Zalecamy, aby na początku postępować zgodnie z tą ścieżką szkoleniową w celu zapewnienia, że dobrze opanujesz podstawowe koncepcje obliczeń kwantowych. Oczywiście możesz pominąć znane sobie tematy, na przykład arytmetykę zespoloną, i poznawać algorytmy w dowolnej kolejności.

### <a name="introduction-to-quantum-computing-concepts"></a>Wprowadzenie do koncepcji obliczeń kwantowych

| Kata | Opis |
|:-----|-------------|
|[Arytmetyka zespolona](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|W tym samouczku objaśniono podstawy matematyczne wymagane do pracy z obliczeniami kwantowymi, takie jak liczby urojone i zespolone.|
|[Algebra liniowa](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|Algebra liniowa służy do przedstawiania kwantowych stanów i operacji w obliczeniach kwantowych. Ten samouczek obejmuje podstawy, w tym macierze i wektory.|
|[Koncepcja kubitu](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Dowiedz się więcej na temat kubitów — jednego z podstawowych pojęć obliczeń kwantowych. |
|[Bramki kwantowe z jednym kubitem](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|W tym samouczku przedstawiono bramki kwantowe z jednym kubitem, które pełnią rolę bloków konstrukcyjnych algorytmów kwantowych i na różne sposoby przekształcają kwantowe stany kubitów.|
|[Systemy z wieloma kubitami](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|W tym samouczku przedstawiono systemy z wieloma kubitami, ich reprezentację w notacji matematycznej i w kodzie Q# oraz pojęcie splątania.|
|[Bramki kwantowe z wieloma kubitami](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Ten samouczek stanowi kolejną część samouczka [Bramki kwantowe z jednym kubitem](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) i koncentruje się na zastosowaniu bram kwantowych do systemów z wieloma kubitami.|

### <a name="quantum-computing-fundamentals"></a>Podstawy obliczeń kwantowych

| Kata | Opis |
|:-----|-------------|
|[Rozpoznawanie bramek kwantowych](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|Seria ćwiczeń mających na celu zapoznanie się z podstawowymi bramkami kwantowymi w języku Q#. Zawiera ćwiczenia dotyczące podstawowych bramek z jednym kubitem i z wieloma kubitami, bramek sprzężonych i kontrolowanych oraz sposobów modyfikowania stanu kubita przy użyciu bramek.|
|[Tworzenie superpozycji kwantowej](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Skorzystaj z tych ćwiczeń, aby zapoznać się z koncepcją superpozycji i z programowaniem w języku Q#. Obejmuje ćwiczenia dotyczące podstawowych bramek z jednym kubitem i z wieloma kubitami, superpozycji oraz kontroli przepływu i rekursji w języku Q#.|
|[Rozróżnianie stanów kwantowych przy użyciu pomiarów](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Rozwiąż te ćwiczenia podczas uczenia się o pomiarach kwantowych oraz o stanach ortogonalnych i nieortogonalnych. |
|[Wspólne pomiary](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Zapoznaj się z informacjami o wspólnych pomiarach parzystości i o tym, jak używać operacji [Miara](xref:microsoft.quantum.intrinsic.measure) do rozróżniania stanów kwantowych.|

### <a name="algorithms"></a>Algorytmy

| Kata | Opis |
|:-----|-------------|
|[Teleportacja kwantowa](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|W tym artykule kata opisano teleportację kwantową — protokół, który pozwala na komunikację stanu kwantowego przy użyciu tylko komunikacji klasycznej i wcześniej udostępnionego splątania kwantowego.|
|[Kodowanie supergęste](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|Kodowanie supergęste to protokół, który umożliwia transmisję dwóch bitów informacji klasycznej przez wysłanie tylko jednego kubitu za pomocą wcześniej udostępnionego splątania kwantowego.  |
|[Algorytm Deutscha-Jozsy](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Ten algorytm słynie z tego, że jest jednym z pierwszych przykładów algorytmu kwantowego, który jest wykładniczo szybszy, niż jakikolwiek deterministyczny algorytm klasyczny.|
|[Badanie właściwości wysokiego poziomu w algorytmie wyszukiwania Grovera](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Ogólne wprowadzenie do jednego z najbardziej znanych algorytmów w obliczeniach kwantowych. Rozwiązuje problem znajdowania danych wejściowych dla czarnej skrzynki (wyrocznia), która generuje określone dane wyjściowe. |
|[Implementowanie algorytmu wyszukiwania Grovera](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Ten artykuł kata bardziej szczegółowo opisuje algorytm wyszukiwania Grovera i obejmuje pisanie wyroczni, wykonywanie kroków algorytmu i łączenie tego wszystkiego w całość.|
|[Rozwiązywanie rzeczywistych problemów przy użyciu algorytmu Grovera: problemy SAT](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Seria ćwiczeń wykorzystujących algorytm Grovera do rozwiązywania rzeczywistych problemów przy użyciu [logicznych problemów spełnialności](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) jako przykładów.  |
|[Rozwiązywanie rzeczywistych problemów przy użyciu algorytmu Grovera: problemy kolorowania grafów](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Ten artykuł kata zawiera dalszy opis algorytmu Grovera, tym razem w kontekście rozwiązywania [problemów z ograniczaniem satysfakcji](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem) na przykładzie problemu kolorowania grafu. |

### <a name="protocols-and-libraries"></a>Protokoły i biblioteki

| Kata | Opis |
|:-----|-------------|
|[Protokół BB84 do dystrybucji kluczy kwantowych](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Poznaj i zaimplementuj protokół dystrybucji kluczy kwantowych, [BB84](https://en.wikipedia.org/wiki/BB84), używając kubitów do wymiany kluczy kryptograficznych. |
|[Kod naprawczy dla błędu przerzucania bitów](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Zapoznaj się z korygowaniem błędów kwantowych przy użyciu najprostszych kodów naprawczych błędów kwantowych (QEC) — trzykubitowego kodu przerzucania bitów.|
|[Szacowanie fazy](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Algorytmy szacowania fazy to jedne z najbardziej podstawowych bloków konstrukcyjnych obliczeń kwantowych. Dowiedz się więcej na temat szacowania faz, korzystając z tych ćwiczeń, które obejmują kwantowe szacowanie fazy oraz przygotowywanie i uruchamianie procedur szacowania fazy w języku Q#.|
|[Arytmetyka kwantowa: tworzenie sumatorów z przeniesieniami szeregowymi](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Seria szczegółowych ćwiczeń, które eksplorują sumowanie [z przeniesieniami szeregowymi](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) na komputerze kwantowym. Utwórz sumator kwantowy w miejscu, rozwiń go za pomocą innego algorytmu, a na końcu utwórz kwantowy układ odejmujący w miejscu.   |

### <a name="entanglement-games"></a>Gry ze splątaniem

| Kata | Opis |
|:-----|-------------|
|[Gra CHSH](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Zapoznaj się ze splątaniem kwantowym na podstawie implementacji gry [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality). Ta [nielokalna](https://en.wikipedia.org/wiki/Quantum_refereed_game) gra pokazuje, w jaki sposób można zastosować splątanie kwantowe, aby zwiększyć szanse graczy na wygraną ponad to, co byłoby możliwe przy strategii czysto klasycznej.|
|[Gra GHZ](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|Gra GHZ to inna gra nielokalna, ale dla trzech graczy.|
|[Gra w kwadrat magiczny Mermina-Peresa](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Seria ćwiczeń, które pozwalają poznać [kwantową pseudo-telepatię](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) zastosowaną do rozwiązania gry w kwadrat magiczny.  |

## <a name="resources"></a>Zasoby

Zobacz pełną serię artykułów [Quantum Kata](https://github.com/microsoft/QuantumKatas)

[Uruchamianie artykułów Kata w trybie online](https://aka.ms/try-quantum-katas)
