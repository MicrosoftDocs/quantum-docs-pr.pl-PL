---
title: Uruchamianie algorytmu wyszukiwania Grovera w języku Q# — Quantum Development Kit
description: Utwórz projekt języka Q#, który pokazuje algorytm Grovera, jeden z kanonicznych algorytmów kwantowych.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443940"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="2f8e3-103">Szybki start: Implementowanie algorytmu wyszukiwania Grovera w języku Q#</span><span class="sxs-lookup"><span data-stu-id="2f8e3-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="2f8e3-104">Z tego przewodnika Szybki start możesz dowiedzieć się, jak opracować i uruchomić wyszukiwanie Grovera w celu przyspieszenia wyszukiwania danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="2f8e3-105">Wyszukiwanie Grovera jest jednym z najpopularniejszych kwantowych algorytmów obliczeniowych, a ta stosunkowo niewielka implementacja w języku Q# umożliwia wstępne poznanie niektórych zalet programowania rozwiązań kwantowych za pomocą ogólnego języka programowania kwantowego Q# w celu tworzenia algorytmów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="2f8e3-106">Na końcu przewodnika zobaczysz dane wyjściowe symulacji, przedstawiające pomyślne znalezienie określonego ciągu na liście nieuporządkowanych wpisów, w ułamku czasu, jaki zajęłoby przeszukanie całej listy na komputerze klasycznym.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="2f8e3-107">Algorytm Grovera wyszukuje określone elementy na liście danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="2f8e3-108">Na przykład pozwala odpowiedzieć na pytanie: czy karta wyciągnięta z talii to as kier?</span><span class="sxs-lookup"><span data-stu-id="2f8e3-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="2f8e3-109">Etykieta określonego elementu jest nazywana _oznaczonymi danymi wejściowymi_.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="2f8e3-110">Przy użyciu algorytmu wyszukiwania Grovera komputer kwantowy gwarantuje wykonanie tego wyszukiwania w mniejszej liczbie kroków niż liczba elementów na przeszukiwanej liście — nie umożliwia tego żaden klasyczny algorytm.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="2f8e3-111">Większa szybkość w przypadku talii kart jest nieznaczna, jednak staje się znacząca w przypadku list z milionami lub miliardami elementów.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="2f8e3-112">Algorytm wyszukiwania Grovera można utworzyć za pomocą zaledwie kilku wierszy kodu.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f8e3-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2f8e3-113">Prerequisites</span></span>

- <span data-ttu-id="2f8e3-114">Zestaw Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="2f8e3-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="2f8e3-115">Do czego służy algorytm wyszukiwania Grovera?</span><span class="sxs-lookup"><span data-stu-id="2f8e3-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="2f8e3-116">Algorytm Grovera pyta, czy element na liście jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="2f8e3-117">Odbywa się to przez utworzenie superpozycji indeksów listy z poszczególnymi współczynnikami (amplitudy prawdopodobieństwa) reprezentującej prawdopodobieństwo tego, że określony indeks jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="2f8e3-118">W algorytmie istnieją dwa kroki, które przyrostowo zwiększają współczynnik szukanego indeksu, do osiągnięcia amplitudy prawdopodobieństwa tego współczynnika równej 1.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="2f8e3-119">Liczba przyrostowych zwiększeń jest mniejsza niż liczba elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="2f8e3-120">Dlatego algorytm wyszukiwania Grovera wykonuje wyszukiwanie w mniejszej liczbie kroków niż klasyczne algorytmy.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagram funkcjonalny algorytmu wyszukiwania Grovera](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="2f8e3-122">Tworzenie kodu</span><span class="sxs-lookup"><span data-stu-id="2f8e3-122">Write the code</span></span>

1. <span data-ttu-id="2f8e3-123">Korzystając z zestawu Quantum Development Kit, [utwórz nowy projekt języka Q#](xref:microsoft.quantum.howto.createproject) o nazwie `Grover` w wybranym środowisku deweloperskim.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="2f8e3-124">Dodaj następujący kod do pliku `Operations.qs` w nowym projekcie:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="2f8e3-125">Aby zdefiniować przeszukiwaną listę, utwórz nowy plik `Reflections.qs` i wklej następujący kod:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="2f8e3-126">Operacja `ReflectAboutMarked` definiuje oznaczone dane wejściowe, które są wyszukiwane: ciąg naprzemiennych wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="2f8e3-127">W tym przykładzie oznaczone dane wejściowe są na stałe umieszczone w kodzie. Przykład można rozszerzyć, aby wyszukać różne dane wejściowe, lub uogólnić, aby wyszukać dowolne dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="2f8e3-128">Następnie uruchom nowy program języka Q#, aby znaleźć element oznaczony przez element `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="2f8e3-129">Język Python z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="2f8e3-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="2f8e3-130">Aby uruchomić nowy program języka Q# z poziomu środowiska Python, zapisz następujący kod jako `host.py`:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="2f8e3-131">Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="2f8e3-132">Język C# z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="2f8e3-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="2f8e3-133">Aby uruchomić nowy program języka Q# z poziomu środowiska C#, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="2f8e3-134">Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2f8e3-135">Język C# w programie Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2f8e3-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="2f8e3-136">Aby uruchomić nowy program języka Q# z poziomu środowiska C# w programie Visual Studio, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="2f8e3-137">Następnie naciśnij klawisz F5. Program zacznie działać i pojawią się nowe okna z następującymi wynikami:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

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

    <span data-ttu-id="2f8e3-138">Operacja `ReflectAboutMarked` jest wywoływana tylko cztery razy, ale program języka Q# mógł znaleźć dane wejściowe „01010” spośród $2^{5} = 32$ możliwych elementów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="2f8e3-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f8e3-139">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="2f8e3-139">Next steps</span></span>

<span data-ttu-id="2f8e3-140">Jeśli ten przewodnik Szybki start Ci się podobał, zapoznaj się z poniższymi zasobami, aby dowiedzieć się więcej o tym, jak za pomocą języka Q# pisać własne aplikacje kwantowe:</span><span class="sxs-lookup"><span data-stu-id="2f8e3-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="2f8e3-141">Wróć do przewodnika Wprowadzenie do zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="2f8e3-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="2f8e3-142">Wypróbuj bardziej ogólny [przykład](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) algorytmu wyszukiwania Grover</span><span class="sxs-lookup"><span data-stu-id="2f8e3-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="2f8e3-143">Dowiedz się więcej o wyszukiwaniu Grovera z artykułów Quantum Kata</span><span class="sxs-lookup"><span data-stu-id="2f8e3-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="2f8e3-144">Przeczytaj więcej o [wzmacnianiu amplitudy](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) — technice obliczeń kwantowych, na której bazuje algorytm wyszukiwania Grovera</span><span class="sxs-lookup"><span data-stu-id="2f8e3-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="2f8e3-145">Pojęcia związane z obliczeniami kwantowymi</span><span class="sxs-lookup"><span data-stu-id="2f8e3-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="2f8e3-146">Przykłady zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="2f8e3-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install