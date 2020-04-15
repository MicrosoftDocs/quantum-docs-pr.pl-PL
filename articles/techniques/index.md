---
title: Techniki projektowania kwantowego
description: Poznaj podstawy tworzenia programów w języku Q#, pracy z operacjami, funkcji, zmiennych i kubitów, a następnie utwórz prosty program kwantowy.
keywords: Nie dodawaj ani nie edytuj słów kluczowych bez konsultacji z ekspertem SEO.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907719"
---
# <a name="quantum-development-techniques"></a>Techniki projektowania kwantowego

W tej sekcji dokumentacji szczegółowo przedstawiono podstawowe pojęcia używane do tworzenia programów kwantowych w języku Q# oraz interakcji z tymi programami z poziomu aplikacji klasycznych.
Zakładamy *pewną* znajomość pojęć dotyczących obliczeń kwantowych, takich jak te opisane w artykule [Pojęcia dotyczące obliczeń kwantowych](xref:microsoft.quantum.concepts.intro), ale nie musisz być ekspertem w zakresie obliczeń kwantowych, aby skorzystać z tych sekcji.

Ich zawartość jest następująca.

- Sekcja [Przegląd programu Q#](xref:microsoft.quantum.techniques.file-structure) zawiera omówienie przeznaczenia i funkcjonalności języka programowania Q#. 
    W szczególności wyjaśniono, dlaczego język Q# *nie* jest językiem służącym tylko do symulowania mechaniki kwantowej, chociaż ta funkcja jest oczywiście udostępniana przez nasz symulator pełnego stanu. 
    Zamiast tego język Q# został zaprojektowany z myślą o przyszłości, a jego programy opisują sposób, w jaki komputer klasycznej kontroli *wchodzi w interakcję* z kubitami. 

- Sekcja [Operacje i funkcje](xref:microsoft.quantum.techniques.opsandfunctions) zawiera szczegóły dwóch wywoływalnych typów w języku Q#: *operacji*, które obejmują akcje względem kubitów i systemów kwantowych, oraz *funkcje*, które współpracują wyłącznie z informacjami klasycznymi. 
    Bez wspólnego działania informacji klasycznych i kwantowych obliczenia kwantowe pozostałyby nieosiągalne. 
    W tej sekcji opisano sposób definiowania i używania tych elementów wywoływalnych w przepływie sterowania programu Q#.

- Sekcja [Zmienne lokalne](xref:microsoft.quantum.techniques.local-variables) opisuje rolę zmiennych w programach Q# oraz sposób ich skutecznego używania. 
    W szczególności poznasz różnice między zmiennymi, których nie można modyfikować, i tymi, które można modyfikować, oraz dowiesz się, jak je przypisywać i przypisywać ponownie.

- Sekcja [Praca z kubitami](xref:microsoft.quantum.techniques.qubits) zawiera opis funkcji języka Q#, których można używać do obsługi pojedynczych kubitów i systemów kubitów. 
    W szczególności oznacza to ich alokację, wykonywanie na nich operacji oraz, ostatecznie, ich pomiar. 
    Ponadto poznasz przydatne techniki związane z przepływem sterowania.

- W sekcji [Zebranie wszystkich elementów](xref:microsoft.quantum.techniques.puttingittogether) użyjesz technik z powyższych sekcji, aby utworzyć program wykonujący **teleportowanie kwantowe**: „teleportowanie” pełnego stanu jednego kubitu do innego przy użyciu dwóch bitów klasycznych.

- Sekcja [Kontynuowanie](xref:microsoft.quantum.techniques.going-further) wprowadza zaawansowane techniki, które mogą okazać się pomocne podczas bardziej złożonego programowania kwantowego. 
    W szczególności omawiamy użycie *parametryzowanych za pomocą typu* operacji i funkcji w języku Q#, które umożliwiają stosowanie przepływu sterowania wyższego rzędu przez niezależność od konkretnych typów danych wejściowych/wyjściowych, a także *pożyczanie* kubitów. 
    Ta ostatnia funkcja różni się od podstawowej alokacji kubitów tym, że operacja języka Q# może używać „zanieczyszczonych” kubitów — tzn. takich, które niekoniecznie zainicjowano do znanego stanu — aby pomóc w obliczeniach.

- W sekcji [Testowanie i debugowanie](xref:microsoft.quantum.techniques.testing-and-debugging) opisano szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami. 
    Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik. 
    Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, do których programiści są przyzwyczajeni, a także tych, które są specyficzne dla programów kwantowych. Obejmuje to tworzenie/uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stan maszyny docelowej. 
    Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. twierdzenia o braku klonowania).


![Kwantowe](~/media/mobius_strip_preview.png)
