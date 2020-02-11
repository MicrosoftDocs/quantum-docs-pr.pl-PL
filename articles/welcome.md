---
uid: microsoft.quantum.welcome
title: Wprowadzenie do zestawu Quantum Development Kit (QDK)
description: Dowiedz się, jak zacząć korzystać z zestawu QDK.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: 066981e3e2fb468c1ff2a4cf4d3e7cff057772ab
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036342"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Wprowadzenie do zestawu Quantum Development Kit (QDK)

Microsoft Quantum Development Kit — Zapraszamy!  
Zestaw QDK zawiera wszystkie narzędzia potrzebne do tworzenia własnych programów i eksperymentów kwantowych przy użyciu języka Q#, czyli języka programowania przeznaczonego specjalnie do programowania aplikacji kwantowych. 

Aby od razu zacząć z niego korzystać, możesz przejść do [przewodnika instalacji zestawu QDK](xref:microsoft.quantum.install).
Następnie przejdziesz przez przewodnik instalowania zestawu Quantum Development Kit na maszynach z systemem Windows, Linux lub MacOS, który pozwoli Ci pisać własne programy kwantowe.

Jeśli nie czujesz się na siłach, aby zacząć programować, ale chcesz dowiedzieć się więcej na temat obliczeń kwantowych i języka Q#, zachęcamy do przeczytania dalszej części tego artykułu, aby uzyskać informacje o zasobach, jakie masz do dyspozycji. W sekcji z [pięcioma pytaniami na temat obliczeń kwantowych](#five-questions-about-quantum-computing) znajdziesz linki do dokładnie tego, czego szukasz.

## <a name="get-started-programming"></a>Wprowadzenie do programowania

Zestaw Quantum Development Kit zapewnia wiele sposobów na nauczenie się, jak pisać programy kwantowe w języku Q#.
Aby zacząć korzystać z możliwości obliczeń kwantowych, możesz wypróbować nasze *przewodniki Szybki start*:

* Aplikacja [kwantowego generatora liczb losowych](xref:microsoft.quantum.quickstarts.qrng) to takie „hello world” w języku Q# , która zapewnia krótkie wprowadzenie do koncepcji kwantowych i umożliwia utworzenie oraz uruchomienie aplikacji kwantowej w ciągu kilku minut.
* [Podstawy obliczeń kwantowych w języku Q#](xref:microsoft.quantum.write-program) obejmują napisanie w języku Q# programu demonstrującego niektóre podstawowe koncepcje programowania kwantowego. 
    Jeśli nie możesz jeszcze zacząć tworzyć kodu, nadal możesz kontynuować bez instalowania zestawu QDK oraz zapoznać się z omówieniem języka programowania Q# i pierwszymi pojęciami związanymi z obliczeniami kwantowymi.
* [Algorytm wyszukiwania Grovera](xref:microsoft.quantum.quickstarts.search) udostępnia przykładowy program w języku Q#, który przedstawia, jak można w tym języku wyrażać algorytmy kwantowe, abstrahując od operacji kwantowych niskiego poziomu. 
    Ten przewodnik Szybki start przeprowadzi Cię przez proces tworzenia programu przy użyciu różnych środowisk programistycznych (hosta języka Python lub hosta języka platformy .NET oraz programu Visual Studio lub Visual Studio Code).

### <a name="learning-further"></a>Dalsza nauka
* Aby dowiedzieć się więcej na temat programowania w języku Q#, zapoznaj się z projektem [Quantum Katas](https://github.com/Microsoft/QuantumKatas) — kolekcją ćwiczeń programistycznych do wykonywania we własnym tempie, które stanowią wprowadzenie do obliczeń kwantowych przez ćwiczenia programistyczne w języku Q#.
    Wiele z tych ćwiczeń kata jest również dostępnych jako notesy języka Q#. 
* Nasze repozytorium [przykładów](https://github.com/Microsoft/Quantum) zawiera wiele próbek tego, jak pisać programy kwantowe przy użyciu języka Q#. Większość z tych przykładów jest pisanych z użyciem naszych [bibliotek kwantowych](https://github.com/Microsoft/QuantumLibraries) typu open source, w tym naszych bibliotek [standardowych](xref:microsoft.quantum.libraries.standard.intro) i [chemicznych](xref:microsoft.quantum.chemistry.concepts.intro) (więcej informacji na ten temat znajduje się poniżej).

## <a name="five-questions-about-quantum-computing"></a>Pięć pytań dotyczących obliczeń kwantowych

Jeśli dopiero zaczynasz programowanie kwantowe, zdajemy sobie sprawę, że to wszystko może nieco zniechęcać. Przygotowaliśmy zasoby ułatwiające przystąpienie do uczenia się obliczeń kwantowych. Jesteśmy przekonani, że dzięki tym krótkim artykułom szybko zechcesz zacząć programować.
* [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what)
* [Co mogą robić komputery kwantowe?](xref:microsoft.quantum.overview.computers)
* [Dlaczego warto uczyć się wykonywania obliczeń kwantowych?](xref:microsoft.quantum.overview.why)
* [Co to jest język Q#?](xref:microsoft.quantum.overview.qsharp)
* [Jak nauczyć się wykonywania obliczeń kwantowych w języku Q#?](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Dokumentacja zestawu Quantum Development Kit

Bieżąca dokumentacja zawiera następujące dodatkowe tematy.

### <a name="using-q"></a>Korzystanie z języka Q#
* W temacie [Techniki programowania kwantowego](xref:microsoft.quantum.techniques.intro) określono podstawowe koncepcje mające zastosowanie przy tworzeniu programów kwantowych w języku Q#. Tematy obejmują struktury plików, operacje i funkcje, pracę z kubitami i trochę zaawansowanych tematów.
* Temat [Dokumentacja języka Q#](xref:microsoft.quantum.language.intro) zawiera szczegółowy opis języka Q#, w tym model typu, wyrażenia, instrukcje i opis korzystania z kompilatora.
* W temacie [Kwantowe symulatory i aplikacje hosta](xref:microsoft.quantum.machines) opisano, jak wykonywane są algorytmy kwantowe, jakie maszyny kwantowe są dostępne oraz jak napisać sterownik inny niż języka Q# dla programu kwantowego.

### <a name="q-libraries"></a>Biblioteki języka Q#
* Temat [Biblioteki standardowe języka Q#](xref:microsoft.quantum.libraries.standard.intro) opisuje operacje i funkcje, które obsługują zarówno klasyczne wymaganie kontroli języka, jak i algorytmy kwantowe w języku Q#. 
    Tematy obejmują przepływ sterowania, struktury danych, korekcję błędów, testowanie i debugowanie. 
* Temat [Biblioteka chemiczna języka Q#](xref:microsoft.quantum.chemistry.concepts.intro) opisuje operacje i funkcje, które obsługują kwantowe symulacje chemiczne będące istotnym zastosowaniem przetwarzania kwantowego. Tematy obejmują między innymi symulowanie dynamiki Hamiltona i szacowanie fazy kwantowej.
* Temat [Biblioteka numeryczna języka Q#](xref:microsoft.quantum.numerics.intro) opisuje operacje i funkcje, które wspierają wyrażanie skomplikowanych funkcji arytmetycznych jako natywnych operacji na maszynach docelowych.
* Temat [Dokumentacja biblioteki języka Q#](xref:microsoft.quantum.standardlibsintro) zawiera informacje referencyjne dotyczące jednostek biblioteki według przestrzeni nazw.

### <a name="general-quantum-computing"></a>Ogólne obliczenia kwantowe
* Temat [Koncepcje z zakresu obliczeń kwantowych](xref:microsoft.quantum.concepts.intro) zawiera takie tematy jak znaczenie algebry liniowej w przetwarzaniu kwantowym, charakter i zastosowanie kubitów, sposób odczytywania obwodu kwantowego i nie tylko.
* Temat [Słownik pojęć z zakresu przetwarzania kwantowego](xref:microsoft.quantum.glossary) zawiera najważniejsze terminy specyficzne dla obliczeń kwantowych i tworzenia programów. 
    Jeśli dopiero wdrażasz się w tę tematykę, ten temat może się przydać jako podręczne źródło informacji podczas czytania naszej dokumentacji.
* Temat [Dalsze informacje](xref:microsoft.quantum.more-information) zawiera specjalnie dobraną dokumentację szczegółowo opisującą obliczenia kwantowe.

### <a name="additional-info"></a>Dodatkowe informacje
* [Informacje o wersji zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Dołącz do społeczności open source języka Q#
Zestaw Quantum Development Kit to zestaw deweloperski typu open source, który pozwala deweloperom uczynić obliczenia kwantowe bardziej dostępnymi dla wszystkich, dzięki czemu możemy rozwiązać niektóre z najważniejszych wyzwań stojących przed ludzkością.  Instytucje akademickie wymagające oprogramowania open source będą mogły wdrożyć język Q# na potrzeby uczenia obliczeń kwantowych i rozwijania ich. Dzięki temu, że zestaw deweloperski jest typu open source, deweloperzy i eksperci z różnych dziedzin mają możliwość współtworzenia ulepszeń i dzielenia się pomysłami za pośrednictwem kodu.

Twoja opinia, uczestnictwo i wkład w zestaw Quantum Development Kit są ważne.  Aby dowiedzieć się więcej na temat źródeł zestawu Quantum Development Kit, przekazać swoją opinię oraz dowiedzieć się, jak można przyczynić się do decyzji dotyczących tej rosnącej platformy programowania kwantowego i wnieść do niej swój wkład, zobacz [Współtworzenie zestawu Quantum Development Kit](xref:microsoft.quantum.contributing).

Jeśli chcesz uzyskać więcej ogólnych informacji na temat inicjatywy obliczeń kwantowych firmy Microsoft, zobacz [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
