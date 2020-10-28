---
title: Współtworzenie dokumentacji do programu Microsoft QDKe
description: Dowiedz się, jak współtworzyć koncepcję lub zawartość interfejsu API w zestawie dokumentacji Microsoft Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2debef858c38b9a8f11264858130ed7cb41543ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691785"
---
# <a name="improving-documentation"></a>Ulepszanie dokumentacji

Dokumentacja zestawu Quantum Development Kit obejmuje kilka różnych formularzy, takich jak informacje są łatwo dostępne dla deweloperów Quantum.

Zgodnie z zasadami dokumentacji [jako kod](https://www.writethedocs.org/guide/docs-as-code/)cała dokumentacja zestawu SDK Development Kit jest formatowana jako kod i jest zarządzana przy użyciu narzędzia Git w taki sam sposób jak kod źródłowy, który jest używany do tworzenia zestawu Quantum Development Kit.
W większości przypadków dokumentacja dotycząca kodu zawiera różne formy [promocji](https://daringfireball.net/projects/markdown/), czyli język pisania sformatowanego tekstu w formacie zwykłego tekstu, który jest łatwy do użycia w wierszu polecenia, w środowisk IDE i z kontrolą źródła.
Podobnie przyjmujemy bibliotekę [MathJax](https://www.mathjax.org/) , aby umożliwić formatowanie matematyczne w dokumentacji przy użyciu języka lateksowego, jak pokazano poniżej.


W ten sposób każda forma dokumentacji różni się nieco w zależności od szczegółów:

- **Dokumentacja dotycząca pojęć** składa się z zestawu artykułów opublikowanych w https://docs.microsoft.com/quantum programie i opisujących wszystkie informacje od podstaw obliczeń opartych na usłudze Quantum do specyfikacji technicznych dla formatów wymiany. Te artykuły są zapisywane w [DocFXej promocji (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), która jest używana do tworzenia rozbudowanych zestawów dokumentacji.
- **Dokumentacja interfejsu API** to zestaw stron dla każdej Q# funkcji, operacji i typu zdefiniowanego przez użytkownika, który jest publikowany w https://docs.microsoft.com/qsharp/api/ . Te strony dokumentują dane wejściowe i operacje do każdego z nich, a także przykłady i linki do dodatkowych informacji. Dokumentacja interfejsu API jest automatycznie wyodrębniana z małych dokumentów DFM w Q# kodzie źródłowym jako część każdej wersji.
- Pliki **README <!----> . MD** dołączone do każdego przykładu i Kata opisują sposób użycia tego przykładu lub Kata są używane, co obejmuje i w jaki sposób odnosi się do reszty zestawu Quantum Development Kit. Te pliki są zapisywane przy użyciu [promocji (GFM) usługi GitHub](https://github.github.com/gfm/), która jest bardziej lekkim rozwiązaniem alternatywnym dla dołączania dokumentacji bezpośrednio do repozytoriów kodu.

## <a name="contributing-to-the-conceptual-documentation"></a>Współtworzenie dokumentacji koncepcyjnej

Aby przyczynić się do usprawnienia dokumentacji koncepcyjnej lub Readme, rozpoczyna się od żądania ściągnięcia do [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)lub [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), zgodnie z potrzebami.
Opiszemy więcej informacji na temat żądań ściągnięcia poniżej, ale teraz istnieje kilka rzeczy, które warto wziąć pod uwagę podczas ulepszania dokumentacji:

- Czytelnicy pochodzą z dokumentacji zestawu Quantum Development Kit z bardzo szerokiego zakresu teł. Wszyscy studenci z dużą szkołą, którzy chcą poznać coś nowego i atrakcyjnego przez nauczyciela z wykorzystaniem analiz Quantum, powinni mieć możliwość uzyskania czegoś z dokumentacji. W zakresie, w jakim jest to możliwe, nie przyjmij szerszej wiedzy na temat tych czytelników, ponieważ mogą one dopiero się rozpoczynać. Jest ona najbardziej przydatna, jeśli można podać jasne i dostępne opisy lub udostępnić linki do innych zasobów, aby uzyskać więcej informacji.
- Zestawy dokumentacji nie są inaczej, jak książki lub dokumenty, w których czytelnicy mogą się pojawić, co może wyglądać jak "środek". Na przykład aparaty wyszukiwania mogą nie zasugerować indeksu lub mogły zostać wysłane przez znajomego próbującego Ci pomóc. Spróbuj, aby pomóc czytelnikowi, zawsze dostarczając jasno kontekst i linki tam, gdzie jest to odpowiednie.
- Niektórzy czytelnicy zobaczą, że abstrakcyjne instrukcje i definicje są najbardziej przydatne, a inne czytelnicy działają najlepiej przez ekstrapolację z konkretnych przykładów. Udostępnienie zarówno ogólnego przypadku, jak i konkretnych przykładów może pomóc obu czytelnikom w największej liczbie programów związanych z programowaniem Quantum.
- Szczególnie jeśli zapisałeś również kod, który jest udokumentowany, elementy mogą być oczywiste, które nie są widoczne dla czytnika. Nie ma żadnego unikatowego najlepszego sposobu programowania, więc niezależnie od tego, jak sprytne lub doświadczony czytelnik nie może się przydać, nie mogą oni odgadnąć od tego, jakie wzorce projektowe okazały się najbardziej pomocne do wyrażania pomysłów w kodzie. Czyszczenie informacji o tym, jak czytelnik może oczekiwać na użycie kodu, może pomóc w udostępnieniu tego kontekstu.
- Wielu członków społeczności programowania Quantum to badacze akademickie i są rozpoznawane głównie przez cytaty dla ich wkładu do społeczności. Oprócz ułatwienia czytelnikom znajdowania dodatkowych materiałów, dzięki czemu warto prawidłowo zamieszczać dane naukowe, takie jak dokumenty, rozmowy, wpisy w blogu i narzędzia programowe, mogą pomóc akademickim współautorom w prowadzeniu najlepszych zadań do ulepszania społeczności.
- Społeczność programowania Quantum jest szeroką i bardzo różnorodną społecznością. Korzystanie z teoretycznych rzeczowników w przykładach innych osób (np.: "Jeśli użytkownik..., będzie..."), może przełączać się, a nie uwzględnić. Firma Cognizant nazwiska osób w cytatach i łączach, a poprawna dołączenie znaków nienależących do zestawu ASCII może zapewnić różnorodność społeczności, wskazując jej składowe. Podobnie wiele wyrazów w języku angielskim jest często używanych w hateful, w taki sposób, że ich użycie w dokumentacji technicznej może spowodować szkody zarówno dla indywidualnych czytelników, jak i dla społeczności.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Odwołuje się do przykładowego kodu z artykułu koncepcyjnego

Jeśli chcesz dołączyć kod z [repozytorium przykładów](https://github.com/Microsoft/Quantum), możesz to zrobić przy użyciu specjalnego DocFX-Flavoredej promocji:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

To polecenie spowoduje zaimportowanie wierszy 4 do 8 [ `Game.qs` pliku z `chsh-game` przykładu](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)i oznaczenie ich jako Q# kodu na potrzeby wyróżniania składni.
Za pomocą tego polecenia można uniknąć duplikowania kodu między artykułami koncepcyjnymi i repozytorium przykładów, aby kod przykładowy w dokumentacji był zawsze aktualny, jak to możliwe.

## <a name="contributing-to-the-api-references"></a>Współtworzenie odwołań do interfejsów API

Aby współtworzyć udoskonalenia odwołań do interfejsów API, warto otworzyć żądanie ściągnięcia bezpośrednio na udokumentowanym kodzie.
Każda funkcja, operacja lub typ zdefiniowany przez użytkownika obsługuje komentarz do dokumentacji (jest to znak `///` zamiast `//` ).
Podczas kompilowania każdej wersji zestawu Quantum Development Kit te komentarze są używane do generowania odniesienia do interfejsu API w https://docs.microsoft.com/qsharp/api/ , w tym szczegółowych informacji o danych wejściowych i wyjść z każdego z nich, założeń, każdy możliwy do przetworzenia i przykłady ich użycia.

> [!IMPORTANT]
> Pamiętaj, aby nie edytować ręcznie wygenerowanej dokumentacji interfejsu API, ponieważ te pliki są zastępowane w każdej nowej wersji.
> Firma Microsoft zastrzega sobie udział w społeczności i chce mieć pewność, że zmiany będą nadal pomocne w udostępnieniu ich przez program.

Rozważmy na przykład funkcję `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
Komentarz dokumentacji powinien pomóc użytkownikowi dowiedzieć się, jak interpretować `bits` i jak `oracle` i do czego służy funkcja.
Każdą z tych informacji można dostarczyć do Q# kompilatora przez specjalną sekcję o nazwie promocji w komentarzu do dokumentacji.
Przykładowo `ControlledOnBitString` możemy napisać coś w następujący sposób:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

Możesz zobaczyć wyrenderowaną wersję kodu powyżej w [dokumentacji interfejsu API dla `ControlledOnBitString` funkcji](xref:Microsoft.Quantum.Canon.ControlledOnBitString).

Oprócz ogólnych metod pisania dokumentacji, w opisie komentarzy dokumentacji interfejsu API pomocne jest zachowanie kilku rzeczy:

- Format każdego komentarza dokumentacji musi być zgodny z Q# oczekiwaniami kompilatora, aby dokumentacja była poprawnie wyświetlana. Niektóre sekcje, takie jak `/// # Remarks` Zezwalaj na zawartość dowolnego kształtu, natomiast sekcje takie jak `/// # See Also` sekcja są bardziej restrykcyjne.
- Czytelnik może odczytać dokumentację interfejsu API w głównej witrynie odniesienia interfejsu API, na podsumowanie dla każdej przestrzeni nazw, a nawet w środowisku IDE za pomocą informacji o aktywowaniu. Upewnienie się, że `/// # Summary` nie jest dłużej niż w przypadku zdania, ułatwia czytelnikowi szybkie sortowanie, czy muszą one zostać odczytane w innym miejscu i może pomóc w szybkim skanowaniu za pomocą podsumowań przestrzeni nazw.
- Dokumentacja może być również w pełni zawracać do samego kodu, ale jest to prawidłowe! Nawet niewielki fragment kodu może mieć nieoczekiwane skutki dla użytkowników, którzy nie znają kontekstu, w którym ten kod istnieje. Dostarczając konkretne przykłady i jasne wyjaśnienia, możesz pomóc użytkownikom w najlepszym użyciu dostępnego dla nich kodu.

<!-- ## LaTeX Formatting ##

**TODO** -->
