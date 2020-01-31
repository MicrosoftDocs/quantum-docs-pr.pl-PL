---
title: Współtworzenie kodu | Microsoft Docs
description: Współtworzenie kodu
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: f9e0f0d9540102331aea64a1245cbaa4833e1e02
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819964"
---
# <a name="contributing-code"></a>Zasady współtworzenia #

Oprócz zgłaszania problemów i ulepszania dokumentacji, współdziałanie kodu z zestawem SDK Development Kit może być bardzo bezpośrednim sposobem, aby pomóc swoim partnerom w społeczności programowania Quantum.
Dzięki objęcie kodu możesz pomóc w rozwiązywaniu problemów, dostarczeniu nowych przykładów, Ułatw korzystanie z istniejących bibliotek, a nawet dodawać zupełnie nowe funkcje.

W tym przewodniku zawarto szczegółowe informacje o tym, czego szukamy, gdy sprawdzimy żądania ściągnięcia, aby pomóc Ci w Twoim udostępnieniu.

## <a name="what-we-look-for"></a>Czego szukamy ##

Idealny udział w kodzie kompiluje się w istniejącej pracy w repozytorium Quantum Development Kit, aby rozwiązać problemy, rozwinąć istniejące funkcje lub dodać nowe funkcje, które znajdują się w zakresie repozytorium.
Gdy akceptujemy wkład kodu, jest on częścią zestawu Quantum Development Kit, w taki sposób, że nowe funkcje zostaną wydane, utrzymane i opracowane w taki sam sposób jak w pozostałej części zestawu Quantum Development Kit.
W ten sposób jest przydatne, gdy funkcje dodane przez wkład są dobrze przetestowane i są udokumentowane.

### <a name="unit-tests"></a>Testy jednostkowe ###

Funkcje Q #, operacje i typy zdefiniowane przez użytkownika, które tworzą biblioteki, takie jak Canon, są automatycznie testowane w ramach opracowywania w repozytorium [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Gdy zostanie otwarte nowe żądanie ściągnięcia, na przykład nasza konfiguracja [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) sprawdzi, czy zmiany w żądaniu ściągnięcia nie podzielą żadnych istniejących funkcji, od których zależy społeczność programowania Quantum.

W przypadku najnowszej wersji Q # test jednostkowy jest definiowany przy użyciu atrybutu `@Test("QuantumSimulator")`. Argument może mieć wartość "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" lub dowolną w pełni kwalifikowaną nazwę określającą cel wykonania. Kilka atrybutów definiujących różne elementy docelowe wykonywania może być dołączanych do tego samego możliwego do odtworzenia. Niektóre z naszych testów nadal używają przestarzałego pakietu [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , który uwidacznia wszystkie funkcje Q # i operacje kończące się `Test` do środowiska [xUnit](https://xunit.github.io/) Framework. Ten pakiet nie jest już wymagany do definiowania testów jednostkowych. 

Poniższa funkcja służy do upewnienia się, że funkcje <xref:microsoft.quantum.canon.fst> i <xref:microsoft.quantum.canon.snd> zwracają odpowiednie dane wyjściowe w reprezentatywnym przykładzie.
Jeśli dane wyjściowe `Fst` lub `Snd` są niepoprawne, instrukcja `fail` jest używana w celu spowodowania niepowodzenia testu.

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

Bardziej skomplikowane warunki można sprawdzić przy użyciu technik w [sekcji Testowanie](xref:microsoft.quantum.libraries.diagnostics) w przewodniku biblioteki standardowe.
Na przykład następujące testy testu, które `H(q); X(q); H(q);` jak wywołane przez <xref:microsoft.quantum.canon.applywith>, są takie same jak `Z(q)`.

```qsharp
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Przy dodawaniu nowych funkcji warto również dodać nowe testy, aby upewnić się, że Twój udział ma odpowiednie znaczenie.
Pomaga to w pozostałej części społeczności do obsługi i opracowywania funkcji, a w szczególności pomaga innym deweloperom wiedzieć, że mogą polegać na funkcji.

> [!NOTE]
> Działa to również w inny sposób.
> Jeśli istnieje funkcja, w której brakuje niektórych testów, to ułatwia nam Dodawanie pokrycia testów.

Lokalnie testy jednostkowe można uruchomić za pomocą Eksploratora testów programu Visual Studio lub polecenia `dotnet test`, dzięki czemu możesz sprawdzić swój udział przed otwarciem żądania ściągnięcia.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>Gdy odrzucimy żądanie ściągnięcia ##

Czasami odrzucimy żądanie ściągnięcia dla udziału.
W takim przypadku nie oznacza to, że jest ona zła, ponieważ istnieje kilka powodów, dla których firma Microsoft może nie być w stanie zaakceptować określonego udziału.
Najprawdopodobniej najczęściej, udział w społeczności programowania Quantum to naprawdę dobry, ale repozytoria zestawu Quantum Development Kit nie są właściwym miejscem do jego opracowywania.
W takich przypadkach zdecydowanie zachęcamy do tworzenia własnego repozytorium---częścią siły zestawu SDK Development Kit jest łatwość tworzenia i rozpowszechniania własnych bibliotek przy użyciu usługi GitHub i NuGet.org, tak samo jak w przypadku dystrybucji firmy Canon i chemii obecnie biblioteki.

W innych przypadkach możemy odrzucić dobry wkład po prostu, ponieważ nie jest to jeszcze gotowe do utrzymania i opracowywania.
Może być trudne do wykonania wszystko, dlatego planujemy, jakie funkcje najlepiej współpracują z planem.
Może to być inny przypadek, gdzie wydawanie funkcji jako biblioteki innej firmy może mieć wiele sensu.
Alternatywnie firma Microsoft może poprosił o pomoc w modyfikowaniu funkcji w celu lepszego dopasowania do naszego planu, dzięki czemu możemy z niego korzystać.

Poprosimy również o wprowadzenie zmian w żądaniu ściągnięcia, jeśli wymaga więcej dokumentacji lub testów jednostkowych, aby ułatwić nam korzystanie z niej lub jeśli jest ona zależna od stylu od pozostałej części bibliotek Q #, które utrudniają użytkownikom znalezienie funkcji.
W takich przypadkach będziemy próbować zaoferować kilka porad w przeglądach kodu na temat tego, co można dodać lub zmienić, aby ułatwić mu dołączenie.

Na koniec nie można zatwierdzić wkładów, które powodują szkody dla społeczności przetwarzania w usłudze [Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).
Chcemy mieć pewność, że wkłady pełnią rolę całej społeczności obliczeniowej usługi Quantum, zarówno w swojej bieżącej różnorodności, jak i w przyszłości, gdy rośnie, aby jeszcze bardziej włączać.
Dziękujemy za pomoc w realizacji tego celu.

## <a name="next-steps"></a>Następne kroki ##

Dziękujemy za pomoc w opracowaniu zestawu Quantum Development Kit doskonałego zasobu dla całej społeczności programistycznej usługi Quantum.
Aby dowiedzieć się więcej, przejdź do poniższego przewodnika dotyczącego stylu Q #.

> [!div class="nextstepaction"]
> [Dowiedz się więcej na temat wytycznych dotyczących stylu Q #](xref:microsoft.quantum.contributing.style)
