---
title: Co to są Q# i QDK?
description: Dowiedz się więcej na temat języka programowania Q#, który został utworzony przez firmę Microsoft do opracowywania aplikacji dla komputerów kwantowych oraz stanowi kluczowy składnik zestawu Quantum Development Kit firmy Microsoft
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907005"
---
# <a name="what-are-q-and-the-qdk"></a>Co to są Q# i QDK?

Q# to język programowania z funkcjami specjalnie zaprojektowanymi do użycia w obliczeniach kwantowych.
Jest to kluczowy składnik zestawu Quantum Development Kit (QDK) firmy Microsoft, który zapewnia programistom kwantowym platformę umożliwiającą skoncentrowanie się na algorytmach bez konieczności zajmowania się kwestiami technicznymi, takimi jak optymalizacja sekwencji bram lub fizyczna implementacja komputera kwantowego.

Zestaw QDK obejmuje szeroki zakres narzędzi zapewniających deweloperom wszystko, czego potrzebują do rozpoczęcia pisania programów kwantowych.
Oprócz języka Q# zestaw SDK zawiera następujące składniki:
* *Biblioteki języka Q#* , które pozwalają deweloperom od razu rozpocząć pracę i tworzyć rzeczywiste aplikacje kwantowe.
* Różne *maszyny docelowe*, na których można uruchamiać programy w języku Q#. Obejmuje to symulatory i estymatory zasobów na potrzeby większych programów kwantowych, a także kwantowy symulator pełnego stanu, który zachowuje się jak bezszumowy komputer kwantowy. To ostatnie narzędzie jest przydatne do wstępnego opracowywania pomysłów, debugowania programów i uczenia się fizyki kwantowej, ale ma wysoką wydajność tylko w przypadku programów o względnie niewielkiej liczbie kubitów. Mamy nadzieję, że w przyszłości będziemy mogli udostępnić sprzęt do obliczeń kwantowych jako maszyny docelowe.
* *Narzędzia* maksymalnie usprawniające pracę z językiem Q#, np. rozszerzenia dla programów Visual Studio i VS Code oraz pakiety do użycia w środowisku Python i notesach Jupyter.
* *Dokumentacja interfejsu API* na potrzeby parowania języka Q# z klasycznymi językami hostów, takimi jak Python i C#.

Aplikacje opracowane za pomocą zestawu Quantum Development Kit firmy Microsoft zwykle składają się z następujących dwóch części:
1. Co najmniej jeden algorytm kwantowy zaimplementowany przy użyciu języka programowania kwantowego Q# i wywoływany przez klasyczny program hosta. Składają się one z następujących elementów: 
    - Operacje Q# — podprocedury zawierające operacje kwantowe 
    - Funkcje Q# — klasyczne podprocedury używane w algorytmie kwantowym.
2. Klasyczny program zaimplementowany w klasycznym języku programowania takim jak Python lub C#, który służy jako główny punkt wejścia i będzie wywoływać operacje języka Q#, gdy będzie konieczne wykonanie algorytmu kwantowego.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Pisanie programów, a nie obwodów kwantowych

Początkowo algorytmy obliczeń kwantowych były wizualizowane jako diagramy, podobne do diagramów obwodów w obliczeniach klasycznych.
Chociaż model obwodowy był przydatny przez wiele lat w badaniach nad obliczeniami kwantowymi, w firmie Microsoft uważamy, że deweloperzy mogą wyjść poza obwody kwantowe i tworzyć algorytmy oraz aplikacje kwantowe przy użyciu języka Q#.
Język Q# został utworzony w celu wykorzystania wiedzy zdobytej podczas dekad tworzenia klasycznego oprogramowania i zapewnia deweloperom kwantowym funkcje języka wysokopoziomowego, które są przeznaczone na potrzeby obliczeń kwantowych.

## <a name="how-does-q-work"></a>Jak działa język Q#?

Język programowania Q# zapewnia intuicyjny zestaw typów, operacji i wyrażeń logicznych służący do opracowywania algorytmów bez konieczności zajmowania się wewnętrzną logiką komputera kwantowego.

Jednym z podstawowych bloków konstrukcyjnych języka Q# jest typ `Qubit`, który jest niemożliwy do skopiowania ani bezpośrednio dostępny, podobnie jak rzeczywisty kubit.
Zamiast tego możemy go zmierzyć, a wyniki pomiaru przechowywać w zmiennej `Result`, która jest typem języka Q# mogącym przyjmować dwie możliwe wartości: `Zero` i `One`.
Takie konstrukcje gwarantują, że algorytmy zawsze przestrzegają praw fizyki kwantowej i mogą działać poprawnie na komputerach kwantowych lub symulatorach.

Język Q# obejmuje również klasyczne funkcje logiki, takie jak wyrażenia warunkowe i pętle z pewnymi dostosowaniami w celu zapewnienia, że wszystkie reguły kwantowe są przestrzegane.
Na przykład sposób wykonywania pętli jest ograniczony, aby upewnić się, że operacje kwantowe nie są wywoływane w funkcjach, które mogą zawierać tylko deterministyczne klasyczne podprocedury.

Programy Q# są często sparowane z programem hosta napisanym w języku C# lub Python, co może zapewnić wygodną organizację kodu klasycznego i kwantowego.
Oprócz obsługi języków takich jak C# i Python, zestaw QDK zapewnia obsługę notesów Jupyter Notebook z użyciem jądra IQ# Jupyter.

## <a name="what-can-i-use-q-for"></a>Do czego mogę używać języka Q#?

### <a name="use-q-to-learn-quantum-computing"></a>Użyj języka Q#, aby nauczyć się wykonywać obliczenia kwantowe

Do tej pory, aby nauczyć się wykonywać obliczenia kwantowe, konieczne było nauczenie się modelu obwodowego w celu zrozumienia algorytmów w postaci uporządkowanych sekwencji bram i pomiarów kwantowych. Dzięki użyciu języka Q# możliwa jest również inna droga: nauka wykonywania obliczeń kwantowych przez pisanie programów kwantowych.

### <a name="use-q-to-design-quantum-algorithms"></a>Projektowanie algorytmów kwantowych za pomocą języka Q#

Język Q# udostępnia coraz więcej bibliotek i typów zdefiniowanych przez użytkowników, które ułatwiają implementowanie narzędzi i tworzenie zaawansowanych algorytmów kwantowych. Przykład: potrzebujesz splątać dwa kubity: q1 i q2? Zamiast indywidualnego stosowania wymaganych bram w celu splątania kubitów możesz użyć już wbudowanej operacji `PrepareEntangledState([q1], [q2])`.

### <a name="use-q-to-estimate-quantum-resources"></a>Szacowanie zasobów kwantowych za pomocą języka Q#

Do symulacji wykonywania programu w języku Q# można używać pełnego symulatora stanów kwantowych, który jest dostarczany z zestawem Quantum Development Kit (QDK).  Zestaw QDK udostępnia też narzędzia do szacowania zasobów, zapewniające wgląd w wydajność programów języka Q#, które są zbyt duże do uruchamiania na symulatorze.  Jest to bardzo przydatne dla projektantów algorytmów, ponieważ mogą oni dostosowywać swoje programy do używania mniejszej ilości zasobów (np. mniejszej liczby kubitów uruchamianych w mniejszej liczbie operacji) w celu uruchamiania ich na starszym sprzęcie kwantowym o mniejszej skali.

### <a name="use-q-to-validate-hardware-performance"></a>Sprawdzanie wydajności sprzętu za pomocą języka Q#

Zaletą języka Q# jest to, że można napisać program raz i uruchamiać go na symulatorach kwantowych w celu debugowania, a także uruchamiać go na różnym kwantowym sprzęcie komputerowym.  Można uruchamiać programy testów porównawczych w języku Q#, aby sprawdzać wydajność sprzętu i porównywać wyniki w miarę rozwoju komputerów kwantowych i pojawiania się nowych.  

## <a name="next-steps"></a>Następne kroki

* [Jak mogę nauczyć się wykonywania obliczeń kwantowych?](xref:microsoft.quantum.overview.learn)
* [Wprowadzenie do zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
