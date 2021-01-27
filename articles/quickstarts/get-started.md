---
uid: microsoft.quantum.welcome
title: Wprowadzenie do zestawu Quantum Development Kit (QDK)
description: Dowiedz się, jak rozpocząć programowanie projektów w języku Q# przy użyciu zestawu Microsoft Quantum Development Kit.
author: bradben
ms.author: v-benbra
ms.date: 9/29/2020
ms.topic: quickstart
no-loc:
- Q#
- $$v
ms.openlocfilehash: 62910becb5b3c7415ac575217230b6c8be55fd7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858858"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Wprowadzenie do zestawu Quantum Development Kit (QDK)

Microsoft Quantum Development Kit — Zapraszamy!  

Zestaw Quantum Development Kit (QDK) zawiera wszystkie narzędzia potrzebne do tworzenia własnych programów i eksperymentów kwantowych przy użyciu języka Q#, czyli języka programowania przeznaczonego specjalnie do programowania aplikacji kwantowych.

Aby od razu rozpocząć pracę, zacznij od [przewodnika po instalowaniu zestawu QDK](xref:microsoft.quantum.install).
Następnie przejdziesz przez przewodnik po instalowaniu zestawu Quantum Development Kit na maszynach z systemem Windows, Linux lub MacOS, który pozwoli Ci pisać własne programy kwantowe.

Jeśli dopiero zaczynasz pracę z obliczeniami kwantowymi, zapoznaj się z sekcją [Omówienie](xref:microsoft.quantum.overview.introduction), aby poznać możliwości komputerów kwantowych i podstawy obliczeń kwantowych.

## <a name="get-started-programming"></a>Wprowadzenie do programowania

Zestaw Quantum Development Kit zapewnia wiele sposobów na nauczenie się, jak pisać programy kwantowe w języku Q#.
Aby zacząć korzystać z możliwości obliczeń kwantowych, możesz wypróbować nasze samouczki:

* [Kwantowy generator liczb losowych](xref:microsoft.quantum.quickstarts.qrng) — to taka aplikacja typu „Hello world” w języku Q#, która zapewnia krótkie wprowadzenie do koncepcji kwantowych i umożliwia utworzenie oraz uruchomienie aplikacji kwantowej w ciągu kilku minut.
* [Eksplorowanie splątania przy użyciu języka Q#](xref:microsoft.quantum.write-program) — ten samouczek obejmuje napisanie w języku Q# programu demonstrującego niektóre podstawowe koncepcje programowania kwantowego. Jeśli nie możesz jeszcze zacząć tworzyć kodu, nadal możesz kontynuować bez instalowania zestawu QDK oraz zapoznać się z omówieniem języka programowania Q# i pierwszymi pojęciami związanymi z obliczeniami kwantowymi.
* [Algorytm wyszukiwania Grovera](xref:microsoft.quantum.quickstarts.search) — poznaj przykładowy program w języku Q#, który przedstawia, jak można w języku Q# wyrażać algorytmy kwantowe, abstrahując od operacji kwantowych niskiego poziomu. Ten samouczek przeprowadzi Cię przez proces tworzenia programu jako aplikacji języka Q# przy użyciu programu Visual Studio lub Visual Studio Code.

## <a name="learning-further"></a>Dalsza nauka
* Witryna Microsoft Learn oferuje bezpłatne szkolenia online dotyczące obliczeń kwantowych. Ścieżka szkoleniowa [Podstawy obliczeń kwantowych](https://docs.microsoft.com/learn/paths/quantum-computing-fundamentals/) przedstawia podstawowe pojęcia związane z obliczeniami kwantowymi i algorytmami kwantowymi oraz umożliwia rozpoczęcie tworzenia programów kwantowych przy użyciu języka Q#.
* Aby dowiedzieć się więcej na temat programowania w języku Q#, zapoznaj się z projektem [Quantum Katas](https://github.com/Microsoft/QuantumKatas) — kolekcją ćwiczeń programistycznych do wykonywania we własnym tempie, które stanowią wprowadzenie do obliczeń kwantowych przez ćwiczenia programistyczne w języku Q#. Wiele z tych ćwiczeń kata jest również dostępnych jako notesy języka Q#. 
* Nasze [repozytorium przykładów](https://github.com/Microsoft/Quantum) zawiera wiele próbek tego, jak pisać programy kwantowe przy użyciu języka Q#. Większość z tych przykładów jest pisanych z użyciem naszych [bibliotek kwantowych](https://github.com/Microsoft/QuantumLibraries) typu open source, w tym naszych bibliotek [standardowych](xref:microsoft.quantum.libraries.standard.intro) i [chemicznych](xref:microsoft.quantum.chemistry.concepts.intro) (więcej informacji na ten temat znajduje się poniżej).

## <a name="key-concepts-for-quantum-computing"></a>Kluczowe pojęcia dotyczące obliczeń kwantowych

Jeśli dopiero zaczynasz programowanie kwantowe, zdajemy sobie sprawę, że to wszystko może nieco zniechęcać. Te kluczowe pojęcia mają ułatwić przejście do środowiska kwantowego i zrozumieć, jak obliczenia kwantowe różnią się od obliczeń klasycznych.

* [Informacje na temat obliczeń kwantowych](xref:microsoft.quantum.overview.understanding)
* [Komputery kwantowe i symulatory kwantowe](xref:microsoft.quantum.overview.simulators)
* [Co to jest język programowania Q# i zestaw QDK?](xref:microsoft.quantum.overview.q-sharp)
* [Algebra liniowa na potrzeby obliczeń kwantowych](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Dokumentacja zestawu Quantum Development Kit

Bieżąca dokumentacja zawiera następujące dodatkowe tematy.

### <a name="no-locq-developer-guides"></a>Przewodniki deweloperów języka Q#

* [Przewodnik użytkownika języka Q#](xref:microsoft.quantum.guide) zawiera szczegółowy opis podstawowych pojęć używanych do tworzenia programów kwantowych w języku Q#.
* W temacie [Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines) opisano, jak są uruchamiane algorytmy kwantowe, jakie maszyny kwantowe są dostępne oraz jak napisać sterownik dla programu kwantowego w języku innym niż Q#.

### <a name="no-locq-libraries"></a>Biblioteki języka Q#

* Temat [Biblioteki standardowe języka Q#](xref:microsoft.quantum.libraries.standard.intro) opisuje operacje i funkcje, które obsługują zarówno wymaganie kontroli języka klasycznego, jak i algorytmy kwantowe w języku Q#. 
    Tematy obejmują przepływ sterowania, struktury danych, korekcję błędów, testowanie i debugowanie. 
* Temat [Biblioteka chemiczna języka Q#](xref:microsoft.quantum.chemistry.concepts.intro) opisuje operacje i funkcje, które obsługują kwantowe symulacje chemiczne będące istotnym zastosowaniem przetwarzania kwantowego. Tematy obejmują między innymi symulowanie dynamiki Hamiltona i szacowanie fazy kwantowej.
* Temat [Biblioteka numeryczna języka Q#](xref:microsoft.quantum.numerics.intro) opisuje operacje i funkcje, które obsługują wyrażanie skomplikowanych funkcji arytmetycznych jako natywnych operacji na maszynach docelowych.
* Temat [Dokumentacja biblioteki języka Q#](xref:microsoft.quantum.apiref-intro) zawiera informacje referencyjne dotyczące jednostek biblioteki według przestrzeni nazw.

### <a name="general-quantum-computing"></a>Ogólne obliczenia kwantowe

* Temat [Koncepcje z zakresu obliczeń kwantowych](xref:microsoft.quantum.concepts.intro) zawiera takie tematy jak znaczenie algebry liniowej w przetwarzaniu kwantowym, charakter i zastosowanie kubitów, sposób odczytywania obwodu kwantowego i nie tylko.
* Temat [Słownik pojęć z zakresu przetwarzania kwantowego](xref:microsoft.quantum.glossary) zawiera najważniejsze terminy specyficzne dla obliczeń kwantowych i tworzenia programów.
    Jeśli dopiero wdrażasz się w tę tematykę, ten temat może się przydać jako podręczne źródło informacji podczas czytania naszej dokumentacji.
* Temat [Dalsze informacje](xref:microsoft.quantum.more-information) zawiera specjalnie dobraną dokumentację szczegółowo opisującą obliczenia kwantowe.

### <a name="additional-info"></a>Dodatkowe informacje

* [Informacje o wersji zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Dołącz do społeczności open-source języka Q#

Zestaw Quantum Development Kit to zestaw deweloperski typu open source, który pozwala deweloperom uczynić obliczenia kwantowe bardziej dostępnymi dla wszystkich, dzięki czemu możemy rozwiązać niektóre z najważniejszych wyzwań stojących przed ludzkością.  Instytucje akademickie wymagające oprogramowania open-source będą mogły wdrożyć język Q# na potrzeby uczenia obliczeń kwantowych i rozwijania ich. Dzięki temu, że zestaw deweloperski jest typu open source, deweloperzy i eksperci z różnych dziedzin mają możliwość współtworzenia ulepszeń i dzielenia się pomysłami za pośrednictwem kodu.

Twoja opinia, uczestnictwo i wkład w zestaw Quantum Development Kit są ważne.  Aby dowiedzieć się więcej na temat źródeł zestawu Quantum Development Kit, przekazać swoją opinię oraz dowiedzieć się, jak można przyczynić się do decyzji dotyczących tej rosnącej platformy programowania kwantowego i wnieść do niej swój wkład, zobacz [Współtworzenie zestawu Quantum Development Kit](xref:microsoft.quantum.contributing).

Jeśli chcesz uzyskać więcej ogólnych informacji na temat inicjatywy obliczeń kwantowych firmy Microsoft, zobacz [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
