---
title: Co mogą robić komputery kwantowe?
description: Dowiedz się więcej o wpływie obliczeń kwantowych — od nowatorskich algorytmów kwantowych do algorytmów inspirowanych kwantowymi i działających na klasycznych komputerach.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529948"
---
# <a name="what-can-a-quantum-computer-do"></a>Co może robić komputer kwantowy?

Co można zrobić za pomocą komputera kwantowego, czego nie można zrobić za pomocą komputera klasycznego?

Rozwiązanie niektórych najtrudniejszych światowych problemów, w przypadku których współczesne komputery musiałyby pracować miliardy lat, zabiera komputerowi kwantowemu dni, godziny lub nawet minuty.

Obliczenia kwantowe pozwolą badaczom na opracowywanie nowych katalizatorów i materiałów, ulepszanie leków, przyspieszenie postępów sztucznej inteligencji oraz odpowiadanie na fundamentalne pytania dotyczące pochodzenia naszego Wszechświata.

## <a name="quantum-simulation"></a>Symulacja kwantowa

Używanie programów kwantowych do modelowania samych systemów kwantowych stwarza ogromny potencjał odkryć prowadzących do innowacji w wielu branżach. Fotosynteza, nadprzewodniki i molekuły złożone to przykłady systemów kwantowych, które mogą być symulowane przy użyciu programów kwantowych.

Symulowanie mikroskopijnych systemów, które zachowują się zgodnie z prawami mechaniki kwantowej, jest obliczeniowo kosztowne. Musimy wziąć pod uwagę wszystkie możliwe stany, które mogą znajdować się w superpozycji, a liczba stanów rośnie wykładniczo z rozmiarem systemu. Na komputerze kwantowym nie trzeba modelować wszystkich stanów systemu. Zamiast tego zagnieżdża się stan kwantowy symulowanego systemu w kubitach samego komputera i uruchamia symulację z określonym zestawem bramek kwantowych. Inaczej mówiąc, używamy komputera kwantowego do symulowania systemu kwantowego.

Cząsteczki chemiczne są systemami kwantowymi i dlatego można je analizować w ten sposób. Jedną z takich specyficznych substancji chemicznych jest enzym _nitrogenaza_, który, po lepszym zrozumieniu jego właściwości, może umożliwić zmniejszenie zużycia energii i emisji gazów cieplarnianych w związku ze stosowaniem nawozów.

## <a name="cryptography"></a>Kryptografia

Prawdopodobnie najbardziej znanym zastosowaniem komputerów kwantowych jest kryptografia, w przypadku której Peter Shor pokazał w 1994 roku, że skalowalny komputer kwantowy może złamać każdą powszechnie używaną technikę szyfrowania.  Kryptografia klasyczna bazuje na niewykonalności operacji na dużych liczbach, takich jak faktoryzacja dużych liczb na dwie liczby pierwsze.

Obliczenia kwantowe sprawiają, że te operacje stają się efektywnie obliczalne w teorii (za pomocą algorytmu Shora). O ile implementacja tego algorytmu nie jest fizycznie możliwa przy obecnej skali sprzętu kwantowego, to spowodował on rozwój algorytmów odpornych na techniki kwantowe w celu zapewnienia bezpieczeństwa danych w przyszłości, w tym nowatorskich algorytmów kwantowych do szyfrowania i dystrybucji kluczy kryptograficznych.

Firma Microsoft ma wiodący na świecie zespół ds. zabezpieczeń i kryptografii postkwantowej, który opracowuje algorytmy odporne na obliczenia kwantowe.

## <a name="optimization"></a>Optymalizacja

Optymalizacja to wielkoskalowe przeszukiwanie wielowymiarowej przestrzeni w celu znalezienia rozwiązania, które minimalizuje daną funkcję kosztu.   Na komputerze kwantowym można przyspieszyć algorytmy optymalizacji, umożliwiając znalezienie rozwiązań, które w przeciwnym razie były nieosiągalne. Zastosowania obejmują transport, logistykę, opiekę zdrowotną, diagnostykę i materiałoznawstwo. Może to mieć istotny wpływ na możliwości usprawniania tych branż.

Optymalizacja przy użyciu obliczeń kwantowych pozwala wprowadzać innowacje dotyczące transportu i logistyki w sposób, który nie jest możliwy we współczesnych systemach klasycznych.

Optymalizacja przepływu ruchu może zmniejszyć zatory.  Oprócz planowania tras istnieją problemy takie jak przypisywanie bramek na lotniskach, dostarczanie paczek i planowanie zadań. Dzięki przełomom w materiałoznawstwie zostaną wprowadzone nowe formy energii, baterie o większej pojemności oraz lżejsze i mocniejsze materiały.

## <a name="machine-learning"></a>Uczenie maszynowe

Bardzo wiele obliczeń numerycznych w przypadku klasycznego przetwarzania danych polega głównie na rozwiązywaniu liniowych systemów równań. Jest to szczególnie prawdziwe w dziedzinie uczenia maszynowego, w której większość kosztów przetwarzania to obliczanie odwrotności ogromnych macierzy.

Na szczęście istnieje algorytm kwantowy, który umożliwia nam określenie przybliżonego rozwiązania systemu wykładniczo szybciej niż w przypadku komputera klasycznego. Ten algorytm otwiera wrota do znacznego przyspieszenia rozwiązywania wszystkich problemów wymagających rozwiązania liniowych systemów równań.

Rozwiązania problemów w tych obszarach będą pomocne w dziedzinach kryzysu energetycznego, zmian klimatu, niedoborów żywności oraz dokładnej i spersonalizowanej diagnostyki medycznej.

## <a name="quantum-inspired-computing"></a>Przetwarzanie inspirowane metodami kwantowymi

Algorytmy inspirowane metodami kwantowymi są implementowane przy użyciu klasycznego oprogramowania, lecz korzystają z zasad kwantowych do zwiększenia szybkości i dokładności.

Algorytmy inspirowane metodami kwantowymi są stosowane w badaniach medycznych. Na przykład do zwiększenia dokładności skanów rezonansu magnetycznego. Przetwarzanie inspirowane metodami kwantowymi jest używane do optymalizowania konfiguracji aparatów do rezonansu magnetycznego na potrzeby identyfikacji konkretnych chorób.

## <a name="next-steps"></a>Następne kroki

* [Dlaczego warto nauczyć się obliczeń kwantowych?](xref:microsoft.quantum.overview.why)
* [Wprowadzenie do zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
