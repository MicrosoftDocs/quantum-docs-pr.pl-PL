---
title: Wkładowanie próbek do programu Microsoft QDKe
description: Dowiedz się, jak współtworzyć przykładowy kod w Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847581"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Wkładowanie próbek do zestawu Quantum Development Kit

Jeśli interesujesz się współtworzeniem kodu do [repozytorium przykładów](https://github.com/Microsoft/Quantum), Dziękujemy za przeprowadzenie społeczności rozwoju Quantum w lepszym miejscu.

## <a name="the-quantum-development-kit-samples-repository"></a>Przykładowe repozytorium zestawu Quantum Development Kit

Aby pomóc Ci w przygotowaniu Twojego wkładu do uzyskania możliwie największej ilości danych, warto szybko zapoznać się z sposobem tworzenia repozytorium przykładów:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Oznacza to, że próbki w [repozytorium Microsoft/Quantum](https://github.com/microsoft/Quantum) są podzielone według obszaru podmiotu w różne foldery, takie jak `algorithms/` , `arithmetic/` , lub `characterization/` .
W folderze dla każdego obszaru tematu każdy przykład składa się z pojedynczego folderu, który zbiera wszystko, co użytkownik musi eksplorować i korzystać z tego przykładu.

## <a name="how-samples-are-structured"></a>Jak przykłady są strukturalne

Przeglądając pliki wchodzące w skład każdego folderu, przyjrzyjmy się do [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) przykładu.

| Plik              | Opis                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# projekt używany do kompilowania próbki przy użyciu zestaw .NET Core SDK |
| `Game.qs`         | Q# operacje i funkcje dla przykładu                 |
| `Host.cs`         | Program hosta C# używany do uruchomienia przykładu                     |
| `host.py`         | Program hosta języka Python używany do uruchomienia przykładu                 |
| `README.md`       | Dokumentacja na temat tego, co robi przykład i jak z niego korzystać    |

Nie wszystkie próbki będą mieć dokładnie ten sam zestaw plików (np.: Niektóre przykłady mogą dotyczyć tylko języka C#, inne mogą nie mieć hosta Python lub niektóre przykłady mogą wymagać Auxillary plików danych).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomia przydatnego pliku Readme

W szczególności jest to `README.md` plik, w którym użytkownicy muszą zacząć korzystać z Twojego przykładu.

Każdy `README.md` z nich powinien rozpoczynać się od pewnych metadanych, które ułatwiają docs.Microsoft.com/samples.

> [!div class="nextstepaction"]
> [Zobacz, jak jest renderowany przykład chsh-Game](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Te metadane są dostępne jako [nagłówek YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) , który wskazuje, jakie języki obejmują przykład (zazwyczaj jest to, `qsharp` `csharp` i `python` ) i jakie produkty obejmuje przykład (zazwyczaj tylko `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`Klucz w nagłówku jest wymagany dla przykładu, który ma być wyświetlany w docs.Microsoft.com/samples.
> Podobnie `product` `language` klucze i mają kluczowe znaczenie dla ułatwienia użytkownikom znajdowania i uruchamiania przykładu.

Po wykonaniu tej czynności warto podać krótkie wprowadzenie, które wskazuje na to, co robi nowy przykład:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Użytkownicy Twojego przykładu będą również wdzięczni za zapoznania się z tym, czego potrzebują, aby je uruchomić (np.: czy użytkownicy potrzebują tylko zestawu Quantum Development Kit lub potrzebują dodatkowego oprogramowania, takiego jak node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

W przypadku wszystkich tych miejsc można poinformować użytkowników, jak uruchomić przykład:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Na koniec warto poinformować użytkowników o tym, co każdy plik w przykładzie robi i gdzie mogą przejść więcej informacji:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Upewnij się, że w tym miejscu Użyj bezwzględnych adresów URL, ponieważ przykład zostanie wyświetlony pod innym adresem URL, gdy jest renderowany w docs.microsoft.com/samples!
