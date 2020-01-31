---
title: Wpółtworzenie zestawu Quantum Development Kit | Microsoft Docs
description: Wpółtworzenie zestawu Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 3f27f7502c83574e6bd8f950d7e17ee481e44a3c
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819862"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Wpółtworzenie zestawu Quantum Development Kit #

Zestaw Quantum Development Kit to więcej niż kolekcja narzędzi do pisania programów kwantowych.
Jest częścią szerokiej społeczności, której członkowie odkrywają przetwarzanie kwantowe, prowadzą badania nad algorytmami kwantowymi, opracowują nowe aplikacje dla urządzeń kwantowych i w inny sposób działają w celu jak najlepszego wykorzystania programowania kwantowego.
Jako element tej społeczności zestaw Quantum Development Kit ma na celu oferowanie deweloperom kwantowym dysponującym różną wiedzą i doświadczeniem funkcje, których potrzebują.
Twój wkład we współtworzenie zestawu Quantum Development Kit pomaga w realizacji tego celu poprzez ulepszanie narzędzi używanych przez innych deweloperów kwantowych, sposobu dokumentowania tych narzędzi, a nawet poprzez tworzenie nowych funkcji i funkcjonalności, dzięki którym cała społeczność programowania kwantowego staje się lepszym miejscem do odkrywania i tworzenia.
Jesteśmy bardzo wdzięczni za Twój wkład i za możliwość współpracy z Tobą w celu uczynienia naszej społeczności jak najlepszą.

W tym przewodniku przedstawiono kilka wskazówek na temat sposobu, w jaki możesz uczynić swój wkład najbardziej przydatnym dla szerszej społeczności programowania kwantowego.

## <a name="building-community"></a>Budowanie społeczności ##

Pierwszą zasadą współtworzenia jest to, że zawsze trzeba mieć na względzie społeczność, do której wnosisz własny wkład.
Działając w sposób profesjonalny i z szacunkiem wobec swoich kolegów oraz wszystkich członków społeczności programowania kwantowego, możesz pomóc zadbać o to, aby Twoje działania tworzyły możliwie najlepszą i najbardziej przyjazną społeczność.

W ramach tych wysiłków wszystkie projekty zestawu Quantum Development Kit przyjęły [Kodeks postępowania oprogramowania Open Source firmy Microsoft](https://opensource.microsoft.com/codeofconduct/).
Aby uzyskać więcej informacji, zobacz [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) (Często zadawane pytania dotyczące kodeksu postępowania) lub wyślij wiadomość e-mail na adres [opencode@microsoft.com](mailto:opencode@microsoft.com) w przypadku jakichkolwiek dodatkowych pytań lub komentarzy.

## <a name="what-kinds-of-contributions-help-the-community"></a>Jakie rodzaje wkładu pomagają społeczności? ##

Poprzez swój wkład możesz pomagać społeczności programowania kwantowego na bardzo wiele różnych sposobów.
W tym przewodniku skoncentrujemy się na trzech z nich, szczególnie istotnych dla zestawu Quantum Development Kit.
Wszystkie one mają kluczowe znaczenie dla tworzenia społeczności programowania kwantowego, która daje ludziom większe możliwości.
Na pewno nie jest to wyczerpująca lista — zachęcamy do eksplorowania innych sposobów pomagania społeczności w spełnianiu obietnic programowania kwantowego!

- **Raportowanie usterek.** Pierwszym krokiem w procesie usuwania usterek i innych rodzajów problemów jest ich zidentyfikowanie. Jeśli znajdziesz usterkę w zestawie Quantum Development Kit, poinformowanie nas o niej pomoże nam ją usunąć i zapewnić lepszy zestaw narzędzi dla społeczności programowania kwantowego.
- **Ulepszanie dokumentacji.** Każdy zestaw dokumentacji zawsze może być lepszy, może obejmować więcej szczegółów i być bardziej dostępny.
- **Współtworzenie kodu.** Oczywiście jednym z najbardziej bezpośrednich sposobów współtworzenia jest dodanie nowego kodu do zestawu Quantum Development Kit.

Wszystkie te różne rodzaje wkładów są niezmiernie wartościowe i bardzo doceniane.
W pozostałej części przewodnika oferujemy porady dotyczące przekazywania poszczególnych rodzajów wkładu.

## <a name="where-do-contributions-go"></a>Gdzie są przekazywane wkłady? ##

Zestaw Quantum Development Kit zawiera wiele różnych elementów, które współpracują ze sobą, aby zrealizować możliwości platformy do pisania programów kwantowych.
Każdy z tych elementów znajduje się w innym repozytorium, więc jedną z pierwszych rzeczy, które należy uporządkować, jest określenie, gdzie każdy wkład będzie najlepiej pasował.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Przykłady i narzędzia ułatwiające rozpoczęcie pracy z zestawem Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Standardowe i specyficzne dla domeny biblioteki zestawu Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Realizowane samodzielnie ćwiczenia programistyczne do nauki obliczeń kwantowych i języka programowania Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Kompilator języka Q#, rozszerzenie programu Visual Studio i rozszerzenie programu Visual Studio Code.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Struktura symulacji, generowanie kodu i maszyny docelowe symulacji dla zestawu Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Jądro Jupyter i funkcje hosta języka Python dla języka Q#, a także obrazy platformy Docker na potrzeby używania IQ# w środowiskach chmur.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Kod źródłowy dokumentacji opublikowanej na stronie https://docs.microsoft.com/quantum.

> [!NOTE]
> Niestety, w tej chwili nie możemy akceptować współtworzenia kodu i dokumentacji w repozytorium [**microsoft/QuantumNC**](https://github.com/microsoft/Quantum-NC), ale nadal będziemy bardzo wdzięczni za raporty o usterkach.

Istnieje również kilka innych, bardziej wyspecjalizowanych repozytoriów, które koncentrują się na różnych zdarzeniach lub pomocniczych funkcjach związanych z zestawem Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): Obsługa formatowania LaTeX dla składni języka Q#.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): Samouczek IQ# Notebook for Deutsch–Jozsa przedstawiony na warsztatach intern workshop 2019 (warsztaty dla stażystów).

## <a name="next-steps"></a>Następne kroki ##

Dziękujemy za uczestnictwo w społeczności zestawu Quantum Development Kit, czekamy na Twój wkład!
Jeśli chcesz dowiedzieć się więcej na temat współtworzenia, przejdź do jednego z poniższych przewodników.

> [!div class="nextstepaction"]
> [Dowiedz się, jak zgłaszać usterki](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Dowiedz się, jak współtworzyć dokumentację](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Dowiedz się, jak otwierać żądania ściągnięcia](xref:microsoft.quantum.contributing.pulls)

