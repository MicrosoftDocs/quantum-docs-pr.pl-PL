---
title: Uruchamianie algorytmu wyszukiwania Grovera w języku Q# — Quantum Development Kit
description: Utwórz projekt języka Q#, który pokazuje algorytm Grovera, jeden z kanonicznych algorytmów kwantowych.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c1fd578fdb3d56a7b48972e6ccc9b1605047fe36
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820355"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Szybki start: Implementowanie algorytmu wyszukiwania Grovera w języku Q#

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

1. Dodaj następujący kod do pliku `Operations.qs` w nowym projekcie:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-23" highlight="5,27":::

1. Aby zdefiniować przeszukiwaną listę, utwórz nowy plik `Reflections.qs` i wklej następujący kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Operacja `ReflectAboutMarked` definiuje oznaczone dane wejściowe, które są wyszukiwane: ciąg naprzemiennych wartości 0 i 1. W tym przykładzie oznaczone dane wejściowe są na stałe umieszczone w kodzie. Przykład można rozszerzyć, aby wyszukać różne dane wejściowe, lub uogólnić, aby wyszukać dowolne dane wejściowe.

1. Następnie uruchom nowy program języka Q#, aby znaleźć element oznaczony przez element `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Język Python z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-python)

    Aby uruchomić nowy program języka Q# z poziomu środowiska Python, zapisz następujący kod jako `host.py`:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[Język C# z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-csharp)

    Aby uruchomić nowy program języka Q# z poziomu środowiska C#, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[Język C# w programie Visual Studio 2019](#tab/tabid-vs2019)

    Aby uruchomić nowy program języka Q# z poziomu środowiska C# w programie Visual Studio, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Następnie naciśnij klawisz F5. Program zacznie działać i pojawią się nowe okna z następującymi wynikami: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    Operacja `ReflectAboutMarked` jest wywoływana tylko cztery razy, ale program języka Q# mógł znaleźć dane wejściowe „01010” spośród $2^{5} = 32$ możliwych elementów wejściowych.

## <a name="next-steps"></a>Następne kroki

Jeśli ten przewodnik Szybki start Ci się podobał, zapoznaj się z poniższymi zasobami, aby dowiedzieć się więcej o tym, jak za pomocą języka Q# pisać własne aplikacje kwantowe:

- [Wróć do przewodnika Wprowadzenie do zestawu QDK](xref:microsoft.quantum.welcome)
- Wypróbuj bardziej ogólny [przykład](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) algorytmu wyszukiwania Grover
- [Dowiedz się więcej o wyszukiwaniu Grovera z artykułów Quantum Kata](xref:microsoft.quantum.overview.katas)
- Przeczytaj więcej o [wzmacnianiu amplitudy](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) — technice obliczeń kwantowych, na której bazuje algorytm wyszukiwania Grovera
- [Pojęcia związane z obliczeniami kwantowymi](xref:microsoft.quantum.concepts.intro)
- [Przykłady zestawu Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
