---
title: Współtworzenie dokumentacji | Microsoft Docs
description: Dokumentacja dotycząca współtworzenia
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183679"
---
# <a name="improving-documentation"></a>Ulepszanie dokumentacji #

Dokumentacja zestawu Quantum Development Kit obejmuje kilka różnych formularzy, takich jak informacje są łatwo dostępne dla deweloperów Quantum.

Zgodnie z zasadami dokumentacji [jako kod](https://www.writethedocs.org/guide/docs-as-code/)cała dokumentacja zestawu SDK Development Kit jest formatowana jako kod i jest zarządzana przy użyciu narzędzia Git w taki sam sposób jak kod źródłowy, który jest używany do tworzenia zestawu Quantum Development Kit.
W większości przypadków dokumentacja dotycząca kodu zawiera różne formy [promocji](https://daringfireball.net/projects/markdown/), czyli język pisania sformatowanego tekstu w formacie zwykłego tekstu, który jest łatwy do użycia w wierszu polecenia, w środowisk IDE i z kontrolą źródła.
Podobnie przyjmujemy bibliotekę [MathJax](https://www.mathjax.org/) , aby umożliwić formatowanie matematyczne w dokumentacji przy użyciu języka lateksowego, jak pokazano poniżej.


W ten sposób każda forma dokumentacji różni się nieco w zależności od szczegółów:

- **Dokumentacja dotycząca pojęć** składa się z zestawu artykułów, które są publikowane w https://docs.microsoft.com/quantum i opisują wszystko, od podstaw obliczeniowych usługi Quantum do specyfikacji technicznych dla formatów wymiany. Te artykuły są zapisywane w [DocFXej promocji (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), która jest używana do tworzenia rozbudowanych zestawów dokumentacji.
- **Dokumentacja interfejsu API** to zestaw stron dla każdej funkcji Q #, operacji i typu zdefiniowanego przez użytkownika, który jest publikowany w https://docs.microsoft.com/qsharp/api/. Te strony dokumentują dane wejściowe i operacje do każdego z nich, a także przykłady i linki do dodatkowych informacji. Odwołanie do interfejsu API jest automatycznie wyodrębniane z małych dokumentów DFM w kodzie kodu źródłowego Q # jako część każdej wersji.
- Pliki **readme<!---->. MD** dołączone do każdego przykładu i Kata opisują, jak używać tego przykładu lub Kata jest używany, co obejmuje, i w jaki sposób odnosi się do reszty zestawu Quantum Development Kit. Te pliki są zapisywane przy użyciu [promocji (GFM) usługi GitHub](https://github.github.com/gfm/), która jest bardziej lekkim rozwiązaniem alternatywnym dla dołączania dokumentacji bezpośrednio do repozytoriów kodu.

## <a name="contributing-to-the-conceptual-documentation"></a>Współtworzenie dokumentacji koncepcyjnej ##

Aby przyczynić się do usprawnienia dokumentacji koncepcyjnej lub Readme, rozpoczyna się od żądania ściągnięcia do [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)lub [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), zgodnie z potrzebami.
Opiszemy więcej informacji na temat żądań ściągnięcia poniżej, ale teraz istnieje kilka rzeczy, które warto wziąć pod uwagę podczas ulepszania dokumentacji:

- Czytelnicy pochodzą z dokumentacji zestawu Quantum Development Kit z bardzo szerokiego zakresu teł. Wszyscy studenci z dużą szkołą, którzy chcą poznać coś nowego i atrakcyjnego przez nauczyciela z wykorzystaniem analiz Quantum, powinni mieć możliwość uzyskania czegoś z dokumentacji. W zakresie, w jakim jest to możliwe, nie przyjmij szerszej wiedzy na temat tych czytelników, ponieważ mogą one dopiero się rozpoczynać. Jest ona najbardziej przydatna, jeśli można podać jasne i dostępne opisy lub udostępnić linki do innych zasobów, aby uzyskać więcej informacji.
- Zestawy dokumentacji nie są inaczej, jak książki lub dokumenty, w których czytelnicy mogą się pojawić, co może wyglądać jak "środek". Na przykład aparaty wyszukiwania mogą nie zasugerować indeksu lub mogły zostać wysłane przez znajomego próbującego Ci pomóc. Spróbuj, aby pomóc czytelnikowi, zawsze dostarczając jasno kontekst i linki tam, gdzie jest to odpowiednie.
- Niektórzy czytelnicy zobaczą, że abstrakcyjne instrukcje i definicje są najbardziej przydatne, a inne czytelnicy działają najlepiej przez ekstrapolację z konkretnych przykładów. Udostępnienie zarówno ogólnego przypadku, jak i konkretnych przykładów może pomóc obu czytelnikom w największej liczbie programów związanych z programowaniem Quantum.
- Szczególnie jeśli zapisałeś również kod, który jest udokumentowany, elementy mogą być oczywiste, które nie są widoczne dla czytnika. Nie ma żadnego unikatowego najlepszego sposobu programowania, więc niezależnie od tego, jak sprytne lub doświadczony czytelnik nie może się przydać, nie mogą oni odgadnąć od tego, jakie wzorce projektowe okazały się najbardziej pomocne do wyrażania pomysłów w kodzie. Czyszczenie informacji o tym, jak czytelnik może oczekiwać na użycie kodu, może pomóc w udostępnieniu tego kontekstu.
- Wielu członków społeczności programowania Quantum to badacze akademickie i są rozpoznawane głównie przez cytaty dla ich wkładu do społeczności. Oprócz ułatwienia czytelnikom znajdowania dodatkowych materiałów, dzięki czemu warto prawidłowo zamieszczać dane naukowe, takie jak dokumenty, rozmowy, wpisy w blogu i narzędzia programowe, mogą pomóc akademickim współautorom w prowadzeniu najlepszych zadań do ulepszania społeczności.
- Społeczność programowania Quantum jest szeroką i bardzo różnorodną społecznością. Korzystanie z teoretycznych rzeczowników w przykładach innych osób (np.: "Jeśli użytkownik..., będzie..."), może przełączać się, a nie uwzględnić. Firma Cognizant nazwiska osób w cytatach i łączach, a poprawna dołączenie znaków nienależących do zestawu ASCII może zapewnić różnorodność społeczności, wskazując jej składowe. Podobnie wiele wyrazów w języku angielskim jest często używanych w hateful, w taki sposób, że ich użycie w dokumentacji technicznej może spowodować szkody zarówno dla indywidualnych czytelników, jak i dla społeczności.

## <a name="contributing-to-the-api-references"></a>Współtworzenie odwołań do interfejsów API ##

Aby współtworzyć udoskonalenia odwołań do interfejsów API, warto otworzyć żądanie ściągnięcia bezpośrednio na udokumentowanym kodzie.
Każda funkcja, operacja lub typ zdefiniowany przez użytkownika obsługuje komentarz do dokumentacji (oznaczone `///` zamiast `//`).
Podczas kompilowania każdej wersji zestawu Quantum Development Kit te komentarze są używane do generowania odniesienia do interfejsu API w https://docs.microsoft.com/qsharp/api/ , w tym szczegółów dotyczących danych wejściowych i wyjściowych z każdego z nich, założeń, każdy możliwy do przetworzenia i przykłady ich użycia.

> [!IMPORTANT]
> Pamiętaj, aby nie edytować ręcznie wygenerowanej dokumentacji interfejsu API, ponieważ te pliki są zastępowane w każdej nowej wersji.
> Firma Microsoft zastrzega sobie udział w społeczności i chce mieć pewność, że zmiany będą nadal pomocne w udostępnieniu ich przez program.

Rozważmy na przykład operację `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
Komentarz dokumentacji powinien pomóc użytkownikowi dowiedzieć się, jak interpretować `angles`, jakie operacje założono na początkowy stan `register`, jaki ma wpływ na `register` i tak dalej.
Każdą z tych informacji można dostarczyć do kompilatora Q # przez specjalną sekcję o nazwie promocji w komentarzu do dokumentacji.
Na przykład `PrepareTrialState`można napisać coś w następujący sposób:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Oprócz ogólnych metod pisania dokumentacji, w opisie komentarzy dokumentacji interfejsu API pomocne jest zachowanie kilku rzeczy:

- Format każdego komentarza do dokumentacji musi być zgodny z tym, co kompilator Q # oczekuje, że dokumentacja będzie poprawnie wyświetlana. Niektóre sekcje, takie jak `/// # Remarks` umożliwiają dostęp do zawartości dowolnego kształtu, podczas gdy sekcje, takie jak sekcja `/// # See Also`, są bardziej restrykcyjne.
- Czytelnik może odczytać dokumentację interfejsu API w głównej witrynie odniesienia interfejsu API, na podsumowanie dla każdej przestrzeni nazw, a nawet w środowisku IDE za pomocą informacji o aktywowaniu. Upewnij się, że `/// # Summary` nie jest dłuższa niż w przypadku zdania, że czytelnik szybko sortuje informacje, czy muszą czytać się dalej lub szukać w innym miejscu i może pomóc w szybkim skanowaniu za pomocą podsumowań przestrzeni nazw.
- Dokumentacja może być również w pełni zawracać do samego kodu, ale jest to prawidłowe! Nawet niewielki fragment kodu może mieć nieoczekiwane skutki dla użytkowników, którzy nie znają kontekstu, w którym ten kod istnieje. Dostarczając konkretne przykłady i jasne wyjaśnienia, możesz pomóc użytkownikom w najlepszym użyciu dostępnego dla nich kodu.

<!-- ## LaTeX Formatting ##

**TODO** -->
