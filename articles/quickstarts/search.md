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
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="6fd52-103">Szybki start: implementowanie algorytmu wyszukiwania Grovera w języku Q\#</span><span class="sxs-lookup"><span data-stu-id="6fd52-103">Quickstart: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="6fd52-104">Z tego przewodnika Szybki start możesz dowiedzieć się, jak opracować i uruchomić wyszukiwanie Grovera w celu przyspieszenia wyszukiwania danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="6fd52-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="6fd52-105">Wyszukiwanie Grovera jest jednym z najpopularniejszych kwantowych algorytmów obliczeniowych, a ta stosunkowo niewielka implementacja w języku Q# umożliwia wstępne poznanie niektórych zalet programowania rozwiązań kwantowych za pomocą ogólnego języka programowania kwantowego Q# w celu tworzenia algorytmów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="6fd52-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="6fd52-106">Na końcu przewodnika zobaczysz dane wyjściowe symulacji, przedstawiające pomyślne znalezienie określonego ciągu na liście nieuporządkowanych wpisów, w ułamku czasu, jaki zajęłoby przeszukanie całej listy na komputerze klasycznym.</span><span class="sxs-lookup"><span data-stu-id="6fd52-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="6fd52-107">Algorytm Grovera wyszukuje określone elementy na liście danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="6fd52-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="6fd52-108">Na przykład pozwala odpowiedzieć na pytanie: czy karta wyciągnięta z talii to as kier?</span><span class="sxs-lookup"><span data-stu-id="6fd52-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="6fd52-109">Etykieta określonego elementu jest nazywana _oznaczonymi danymi wejściowymi_.</span><span class="sxs-lookup"><span data-stu-id="6fd52-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="6fd52-110">Przy użyciu algorytmu wyszukiwania Grovera komputer kwantowy gwarantuje wykonanie tego wyszukiwania w mniejszej liczbie kroków niż liczba elementów na przeszukiwanej liście — nie umożliwia tego żaden klasyczny algorytm.</span><span class="sxs-lookup"><span data-stu-id="6fd52-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="6fd52-111">Większa szybkość w przypadku talii kart jest nieznaczna, jednak staje się znacząca w przypadku list z milionami lub miliardami elementów.</span><span class="sxs-lookup"><span data-stu-id="6fd52-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="6fd52-112">Algorytm wyszukiwania Grovera można utworzyć za pomocą zaledwie kilku wierszy kodu.</span><span class="sxs-lookup"><span data-stu-id="6fd52-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6fd52-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="6fd52-113">Prerequisites</span></span>

- <span data-ttu-id="6fd52-114">Zestaw Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="6fd52-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="6fd52-115">Do czego służy algorytm wyszukiwania Grovera?</span><span class="sxs-lookup"><span data-stu-id="6fd52-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="6fd52-116">Algorytm Grovera pyta, czy element na liście jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="6fd52-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="6fd52-117">Odbywa się to przez utworzenie superpozycji indeksów listy z poszczególnymi współczynnikami (amplitudy prawdopodobieństwa) reprezentującej prawdopodobieństwo tego, że określony indeks jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="6fd52-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="6fd52-118">W algorytmie istnieją dwa kroki, które przyrostowo zwiększają współczynnik szukanego indeksu, do osiągnięcia amplitudy prawdopodobieństwa tego współczynnika równej 1.</span><span class="sxs-lookup"><span data-stu-id="6fd52-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="6fd52-119">Liczba przyrostowych zwiększeń jest mniejsza niż liczba elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="6fd52-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="6fd52-120">Dlatego algorytm wyszukiwania Grovera wykonuje wyszukiwanie w mniejszej liczbie kroków niż klasyczne algorytmy.</span><span class="sxs-lookup"><span data-stu-id="6fd52-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagram funkcjonalny algorytmu wyszukiwania Grovera](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="6fd52-122">Tworzenie kodu</span><span class="sxs-lookup"><span data-stu-id="6fd52-122">Write the code</span></span>

1. <span data-ttu-id="6fd52-123">Korzystając z zestawu Quantum Development Kit, [utwórz nowy projekt języka Q#](xref:microsoft.quantum.howto.createproject) o nazwie `Grover` w wybranym środowisku deweloperskim.</span><span class="sxs-lookup"><span data-stu-id="6fd52-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="6fd52-124">Dodaj następujący kod do pliku `Program.qs` w nowym projekcie:</span><span class="sxs-lookup"><span data-stu-id="6fd52-124">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="6fd52-125">Aby zdefiniować przeszukiwaną listę, utwórz nowy plik `Reflections.qs` i wklej następujący kod:</span><span class="sxs-lookup"><span data-stu-id="6fd52-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="6fd52-126">Operacja `ReflectAboutMarked` definiuje oznaczone dane wejściowe, które są wyszukiwane: ciąg naprzemiennych wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="6fd52-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="6fd52-127">W tym przykładzie oznaczone dane wejściowe są na stałe umieszczone w kodzie. Przykład można rozszerzyć, aby wyszukać różne dane wejściowe, lub uogólnić, aby wyszukać dowolne dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="6fd52-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="6fd52-128">Następnie uruchom nowy program języka Q#, aby znaleźć element oznaczony przez element `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="6fd52-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="6fd52-129">Aplikacje wiersza polecenia języka Q# w programie Visual Studio lub Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6fd52-129">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="6fd52-130">Plik wykonywalny uruchomi operację lub funkcję oznaczoną atrybutem `@EntryPoint()` w symulatorze lub estymatorze zasobów, w zależności od konfiguracji projektu i opcji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="6fd52-130">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="6fd52-131">W programie Visual Studio wystarczy nacisnąć klawisze Ctrl + F5, aby wykonać skrypt.</span><span class="sxs-lookup"><span data-stu-id="6fd52-131">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="6fd52-132">W programie VS Code za pierwszym razem skompiluj plik `Program.qs`, wpisując w terminalu następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="6fd52-132">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="6fd52-133">Przy kolejnych uruchomieniach nie musisz ponownie kompilować pliku.</span><span class="sxs-lookup"><span data-stu-id="6fd52-133">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="6fd52-134">Aby go uruchomić, wprowadź następujące polecenie i naciśnij klawisz Enter:</span><span class="sxs-lookup"><span data-stu-id="6fd52-134">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="6fd52-135">W terminalu powinien zostać wyświetlony następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="6fd52-135">You should see the following message displayed in the terminal:</span></span>

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

<span data-ttu-id="6fd52-136">Dzieje się tak, ponieważ nie określono liczby kubitów do użycia, a więc w terminalu wyświetlane są polecenia dostępne na potrzeby pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="6fd52-136">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="6fd52-137">Jeśli chcesz użyć 5 kubitów, wpisz:</span><span class="sxs-lookup"><span data-stu-id="6fd52-137">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="6fd52-138">Po naciśnięciu klawisza Enter powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="6fd52-138">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="6fd52-139">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="6fd52-139">Next steps</span></span>

<span data-ttu-id="6fd52-140">Jeśli ten przewodnik Szybki start Ci się podobał, zapoznaj się z poniższymi zasobami, aby dowiedzieć się więcej o tym, jak za pomocą języka Q# pisać własne aplikacje kwantowe:</span><span class="sxs-lookup"><span data-stu-id="6fd52-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="6fd52-141">Wróć do przewodnika Wprowadzenie do zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="6fd52-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="6fd52-142">Wypróbuj bardziej ogólny [przykład](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) algorytmu wyszukiwania Grover</span><span class="sxs-lookup"><span data-stu-id="6fd52-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="6fd52-143">Dowiedz się więcej o wyszukiwaniu Grovera z artykułów Quantum Kata</span><span class="sxs-lookup"><span data-stu-id="6fd52-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="6fd52-144">Przeczytaj więcej o [wzmacnianiu amplitudy][amplitude-amplification] — technice obliczeń kwantowych, na której bazuje algorytm wyszukiwania Grovera</span><span class="sxs-lookup"><span data-stu-id="6fd52-144">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="6fd52-145">Pojęcia związane z obliczeniami kwantowymi</span><span class="sxs-lookup"><span data-stu-id="6fd52-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="6fd52-146">Przykłady zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="6fd52-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
