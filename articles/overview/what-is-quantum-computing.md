---
title: Co to są obliczenia kwantowe?
description: Wprowadzenie do funkcji, algorytmów i sprzętu związanych z obliczeniami kwantowymi oraz do zestawu Microsoft Quantum Development Kit (QDK).
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 668df50882272bfa56541f178e2f4d5fb35efcf5
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906784"
---
# <a name="what-is-quantum-computing"></a>Co to są obliczenia kwantowe?

Istnieją pewne problemy tak niesamowicie trudne i złożone, że nawet jeśli wszystkie superkomputery na świecie pracowałyby nad ich rozwiązaniem, to będzie to trwało dłużej niż okres istnienia wszechświata.

Komputery kwantowe dają nadzieję na rozwiązanie niektórych największych wyzwań dla naszej planety — tych związanych ze środowiskiem, rolnictwem, medycyną, energetyką, klimatem i materiałoznawstwem, oraz tych, które dopiero się pojawią. Komputery kwantowe staną się ogromnie ważne, a ich odkrycie będzie porównywane do utworzenia tranzystora w 1947 roku, co stanowiło podstawę dla dzisiejszej gospodarki cyfrowej.

Obliczenia kwantowe wykorzystują unikatowe właściwości fizyki kwantowej, aby zapewnić nowy i zaawansowany model obliczeń. Teoria fizyki kwantowej stanowi, że materia na poziomie kwantowym może znajdować się w superpozycji wielu klasycznych stanów. Te stany oddziałują natomiast na siebie jak fale rozbijające się na nadmorskich skałach.  Stan materii po wykonaniu pomiaru ulega „kolapsowi” do jednego ze stanów klasycznych. 

Następne powtórzenia tego samego pomiaru dają taki sam wynik klasyczny.  Splątanie kwantowe występuje, gdy cząstki oddziałują w taki sposób, że stan kwantowy każdej z nich nie może być opisany niezależnie od innych, nawet jeśli cząstki są fizycznie oddalone.  

Obliczenia kwantowe przechowują informacje w stanach kwantowych oraz wykorzystują ich kwantowe zjawiska superpozycji i splątania, aby realizować operacje kwantowe przeprowadzające obliczenia na tych informacjach, tym samym wykorzystując interferencję kwantową i ucząc się programowania jej.

Obliczenia kwantowe mogą wydawać się onieśmielające, ale posiadając odpowiednie zasoby możesz już teraz rozpocząć tworzenie aplikacji kwantowych.

## <a name="the-qubit"></a>Kubit

Obliczenia kwantowe definiują koncepcje obliczeniowe odzwierciedlające zachowanie kwantowe.  Obliczenia kwantowe zaczynają się od koncepcji kubitu.  W obliczeniach kwantowych bit kwantowy — **kubit** — jest jednostką informacji kwantowej, tak jak bit klasyczny. Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast kubit może być w stanie **superpozycji** wartości 0 i 1 równocześnie.  

Dokonanie pomiaru kubitu zmienia jego stan. Podczas pomiaru kubit przechodzi z superpozycji do jednego ze stanów klasycznych.  

Ponadto wiele kubitów może być **splątanych**. Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.

## <a name="quantum-algorithms"></a>Algorytmy kwantowe

Algorytmy kwantowe projektuje się w celu korzystania ze zjawisk i zachowań kwantowych, aby przyspieszyć algorytmy klasyczne lub zapewnić zupełnie nowe sposoby modelowania systemów fizycznych.  Te algorytmy wykorzystują sposób kodowania informacji przez kubity oraz równoległy charakter operacji na wielu splątanych kubitach w superpozycji.  

Komputery klasyczne kodują informacje w bitach — każdy bit koduje dwie możliwe wartości: 0 lub 1.  Jeden kubit koduje dwie wartości równocześnie (0 i 1).  Dwa bity klasyczne kodują jedną z czterech możliwych wartości (00, 01, 10, 11), natomiast dwa kubity kodują dowolną superpozycję tych czterech stanów równocześnie, chociaż można uzyskać tylko jedną z tych wartości podczas mierzenia. Cztery kubity kodują dowolną superpozycję 16 wartości równocześnie, i tak dalej, wykładniczo.  100 kubitów może zakodować więcej informacji, niż jest obecnie dostępne w największych systemach komputerowych.  

Co więcej, gdy wiele splątanych kubitów działa w spójny sposób, mogą one przetwarzać wiele opcji jednocześnie. Splątane kubity mogą przetwarzać informacje w ułamku czasu, jaki byłby potrzebny nawet najszybszym systemom niekwantowym.

Wykorzystanie tych cech kwantowych było celem badań algorytmów kwantowych przez wiele dekad. Znaleziono wiele innowacyjnych technik rozwiązywania problemów w ułamku czasu potrzebnego do rozwiązania klasycznego.  

Jednym z najpopularniejszych algorytmów kwantowych jest _algorytm Shora_ na potrzeby faktoryzacji, który sprawia, że klasycznie nieobliczalny problem faktoryzacji dużej liczby na dwie liczby pierwsze (zgodnie z tradycyjną kryptografią) staje się możliwy do obliczenia.

Jeśli chodzi o zastosowania bardziej praktyczne, to dzięki użyciu superpozycji, spętlenia kwantowego i **nieklonowalności** kubitów możliwe jest tworzenie algorytmów służących do zabezpieczania dystrybucji kluczy kryptograficznych, co uniemożliwi kopiowanie kubitów bez wykrycia tego faktu.

_Algorytm Grovera_ przedstawia technikę algorytmu kwantowego, która zapewnia kwadratowe przyspieszenie wyszukiwania danych bez struktury.

## <a name="quantum-hardware"></a>Sprzęt kwantowy

W przypadku komputerów klasycznych bity odpowiadają poziomom napięcia w obwodach krzemu. Sprzęt do obliczeń kwantowych można zaimplementować za pomocą wielu różnych fizycznych realizacji kubitów: uwięzione jony, nadprzewodnictwo, neutrony, spin elektronów, polaryzacja światła i kubity topologiczne. Sprzęt kwantowy to nowo powstała technologia. Kubity są z natury wrażliwe i stają się mniej spójne w trakcie interakcji ze swoim środowiskiem. Wymagane jest zrównoważenie dokładności systemu i skalowalności. Im większa skala (czyli liczba kubitów), tym większy jest współczynnik błędów.

Firma Microsoft opracowuje komputer kwantowy oparty na kubitach topologicznych. Wierzymy, że kubit topologiczny będzie mniej zależny od zmian w środowisku, co z kolei spowoduje ograniczenie liczby procesów naprawiania błędów zewnętrznych. Funkcja kubitów topologicznych zwiększa stabilność i odporność na zakłócenia środowiskowe, co oznacza, że kubity mogą być łatwiej skalowane i dłużej pozostać niezawodnie.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Obliczenia kwantowe — pełny stos sprzętu i oprogramowania

Program technologii kwantowych firmy Microsoft jest unikatowy, ponieważ koncentrujemy się na skalowaniu każdego składnika systemu, aby umożliwić rzeczywiste zastosowania rozwiązań kwantowych. To kompleksowe podejście obejmuje:

* opracowanie komputera kwantowego z użyciem kubitów topologicznych, które będą niezawodne, skalowalne i odporne na błędy; 
* opracowanie unikatowej kriogenicznej płaszczyzny sterowania z niskim zużyciem energii i rozpraszaniem ciepła; 
* opracowanie kompletnego stosu oprogramowania umożliwiającego programowanie komputera kwantowego i kontrolowanie takiego systemu na dużą skalę.

Zestaw typu open source o nazwie Quantum Development Kit (QDK) został wprowadzony w celu zwiększenia dostępności programowania kwantowego i tworzenia algorytmów kwantowych. Język programowania wysokiego poziomu Q# pozwala rozwiązywać problemy programowania kwantowego.  Zaprojektowaliśmy język Q# jako kwantowy język programowania wysokiego poziomu, koncentrujący się na tworzeniu algorytmów i aplikacji. Kompilator języka Q# jest zintegrowany ze stosem oprogramowania, co umożliwia kompilowanie algorytmów kwantowych aż do pierwotnych operacji komputera kwantowego.  Do określonej skali (wyrażanej liczbą kubitów) obliczenia kwantowe mogą być symulowane na klasycznym komputerze. Korzystając z symulacji możesz już dziś zacząć pisać programy kwantowe, które będą mogły być w przyszłości uruchamiane na sprzęcie kwantowym.  Dołączyliśmy też do języka Q# przykłady, biblioteki i ćwiczenia, aby ułatwić rozpoczęcie programowania kwantowego już dziś. 

## <a name="next-steps"></a>Następne kroki

* [Co mogą robić komputery kwantowe?](xref:microsoft.quantum.overview.computers)
* [Wprowadzenie do zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Przeczytaj więcej o [pojęciach dotyczących obliczeń kwantowych](xref:microsoft.quantum.concepts.intro)
