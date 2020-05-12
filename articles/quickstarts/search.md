---
title: Uruchamianie algorytmu wyszukiwania Grovera w języku Q# — Quantum Development Kit
description: Utwórz projekt języka Q#, który pokazuje algorytm Grovera, jeden z kanonicznych algorytmów kwantowych.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686823"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Szybki start: implementowanie algorytmu wyszukiwania Grovera w języku Q\#

Z tego przewodnika Szybki start możesz dowiedzieć się, jak opracować i uruchomić wyszukiwanie Grovera w celu przyspieszenia wyszukiwania danych bez struktury.  Wyszukiwanie Grovera jest jednym z najpopularniejszych kwantowych algorytmów obliczeniowych, a ta stosunkowo niewielka implementacja w języku Q# umożliwia wstępne poznanie niektórych zalet programowania rozwiązań kwantowych za pomocą ogólnego języka programowania kwantowego Q# w celu tworzenia algorytmów kwantowych.  Na końcu przewodnika zobaczysz dane wyjściowe symulacji, przedstawiające pomyślne znalezienie określonego ciągu na liście nieuporządkowanych wpisów, w ułamku czasu, jaki zajęłoby przeszukanie całej listy na komputerze klasycznym.

Algorytm Grovera wyszukuje określone elementy na liście danych bez struktury. Na przykład pozwala odpowiedzieć na pytanie: czy karta wyciągnięta z talii to as kier? Etykieta określonego elementu jest nazywana _oznaczonymi danymi wejściowymi_.

Przy użyciu algorytmu wyszukiwania Grovera komputer kwantowy gwarantuje wykonanie tego wyszukiwania w mniejszej liczbie kroków niż liczba elementów na przeszukiwanej liście — nie umożliwia tego żaden klasyczny algorytm. Większa szybkość w przypadku talii kart jest nieznaczna, jednak staje się znacząca w przypadku list z milionami lub miliardami elementów.

Algorytm wyszukiwania Grovera można utworzyć za pomocą zaledwie kilku wierszy kodu.

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Do czego służy algorytm wyszukiwania Grovera?

Algorytm Grovera pyta, czy element na liście jest wyszukiwany. Odbywa się to przez utworzenie superpozycji indeksów listy z poszczególnymi współczynnikami (amplitudy prawdopodobieństwa) reprezentującej prawdopodobieństwo tego, że określony indeks jest wyszukiwany.

W algorytmie istnieją dwa kroki, które przyrostowo zwiększają współczynnik szukanego indeksu, do osiągnięcia amplitudy prawdopodobieństwa tego współczynnika równej 1.

Liczba przyrostowych zwiększeń jest mniejsza niż liczba elementów na liście. Dlatego algorytm wyszukiwania Grovera wykonuje wyszukiwanie w mniejszej liczbie kroków niż klasyczne algorytmy.

![Diagram funkcjonalny algorytmu wyszukiwania Grovera](~/media/grover.png)

## <a name="write-the-code"></a>Tworzenie kodu

1. Korzystając z zestawu Quantum Development Kit, [utwórz nowy projekt języka Q#](xref:microsoft.quantum.howto.createproject) o nazwie `Grover` w wybranym środowisku deweloperskim.

1. Dodaj następujący kod do pliku `Program.qs` w nowym projekcie:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Aby zdefiniować przeszukiwaną listę, utwórz nowy plik `Reflections.qs` i wklej następujący kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Operacja `ReflectAboutMarked` definiuje oznaczone dane wejściowe, które są wyszukiwane: ciąg naprzemiennych wartości 0 i 1. W tym przykładzie oznaczone dane wejściowe są na stałe umieszczone w kodzie. Przykład można rozszerzyć, aby wyszukać różne dane wejściowe, lub uogólnić, aby wyszukać dowolne dane wejściowe.

1. Następnie uruchom nowy program języka Q#, aby znaleźć element oznaczony przez element `ReflectAboutMarked`.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Aplikacje wiersza polecenia języka Q# w programie Visual Studio lub Visual Studio Code

Plik wykonywalny uruchomi operację lub funkcję oznaczoną atrybutem `@EntryPoint()` w symulatorze lub estymatorze zasobów, w zależności od konfiguracji projektu i opcji wiersza polecenia.

W programie Visual Studio wystarczy nacisnąć klawisze Ctrl + F5, aby wykonać skrypt.

W programie VS Code za pierwszym razem skompiluj plik `Program.qs`, wpisując w terminalu następujące polecenie:

```Command line
dotnet build
```

Przy kolejnych uruchomieniach nie musisz ponownie kompilować pliku. Aby go uruchomić, wprowadź następujące polecenie i naciśnij klawisz Enter:

```Command line
dotnet run --no-build
```

W terminalu powinien zostać wyświetlony następujący komunikat:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Dzieje się tak, ponieważ nie określono liczby kubitów do użycia, a więc w terminalu wyświetlane są polecenia dostępne na potrzeby pliku wykonywalnego. Jeśli chcesz użyć 5 kubitów, wpisz:

```Command line
dotnet run --n-qubits 5
```

Po naciśnięciu klawisza Enter powinny zostać wyświetlone następujące dane wyjściowe:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Następne kroki

Jeśli ten przewodnik Szybki start Ci się podobał, zapoznaj się z poniższymi zasobami, aby dowiedzieć się więcej o tym, jak za pomocą języka Q# pisać własne aplikacje kwantowe:

- [Wróć do przewodnika Wprowadzenie do zestawu QDK](xref:microsoft.quantum.welcome)
- Wypróbuj bardziej ogólny [przykład](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) algorytmu wyszukiwania Grover
- [Dowiedz się więcej o wyszukiwaniu Grovera z artykułów Quantum Kata](xref:microsoft.quantum.overview.katas)
- Przeczytaj więcej o [wzmacnianiu amplitudy][amplitude-amplification] — technice obliczeń kwantowych, na której bazuje algorytm wyszukiwania Grovera
- [Pojęcia związane z obliczeniami kwantowymi](xref:microsoft.quantum.concepts.intro)
- [Przykłady zestawu Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
