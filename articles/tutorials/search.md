---
title: Uruchom algorytm wyszukiwania Grover w Q# -Quantum Development Kit
description: Kompiluj Q# projekt, który demonstruje algorytm Grover, jeden z kanonicznych algorytmów Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: f2ae56bdca893e8a317c16d0a993da15b9f021b5
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863123"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="e61c6-103">Samouczek: implementowanie algorytmu wyszukiwania Grovera w języku Q\#</span><span class="sxs-lookup"><span data-stu-id="e61c6-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="e61c6-104">Z tego samouczka możesz dowiedzieć się, jak opracować i uruchomić wyszukiwanie Grovera w celu przyspieszenia wyszukiwania danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="e61c6-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="e61c6-105">Wyszukiwanie Grover jest jednym z najpopularniejszych algorytmów obliczeniowych, a ta stosunkowo mała Q# implementacja zapewnia pewne zalety programowania rozwiązań Quantum przy użyciu ogólnego Q# języka przetwarzania Quantum do wyrażenia Quantum.</span><span class="sxs-lookup"><span data-stu-id="e61c6-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="e61c6-106">Na końcu przewodnika zobaczysz dane wyjściowe symulacji, przedstawiające pomyślne znalezienie określonego ciągu na liście nieuporządkowanych wpisów, w ułamku czasu, jaki zajęłoby przeszukanie całej listy na komputerze klasycznym.</span><span class="sxs-lookup"><span data-stu-id="e61c6-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="e61c6-107">Algorytm Grovera wyszukuje określone elementy na liście danych bez struktury.</span><span class="sxs-lookup"><span data-stu-id="e61c6-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="e61c6-108">Na przykład pozwala odpowiedzieć na pytanie: czy karta wyciągnięta z talii to as kier?</span><span class="sxs-lookup"><span data-stu-id="e61c6-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="e61c6-109">Etykieta określonego elementu jest nazywana _oznaczonymi danymi wejściowymi_.</span><span class="sxs-lookup"><span data-stu-id="e61c6-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="e61c6-110">Przy użyciu algorytmu wyszukiwania Grovera komputer kwantowy gwarantuje wykonanie tego wyszukiwania w mniejszej liczbie kroków niż liczba elementów na przeszukiwanej liście — nie umożliwia tego żaden klasyczny algorytm.</span><span class="sxs-lookup"><span data-stu-id="e61c6-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="e61c6-111">Większa szybkość w przypadku talii kart jest nieznaczna, jednak staje się znacząca w przypadku list z milionami lub miliardami elementów.</span><span class="sxs-lookup"><span data-stu-id="e61c6-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="e61c6-112">Algorytm wyszukiwania Grovera można utworzyć za pomocą zaledwie kilku wierszy kodu.</span><span class="sxs-lookup"><span data-stu-id="e61c6-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e61c6-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="e61c6-113">Prerequisites</span></span>

- <span data-ttu-id="e61c6-114">Zestaw Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="e61c6-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="e61c6-115">Do czego służy algorytm wyszukiwania Grovera?</span><span class="sxs-lookup"><span data-stu-id="e61c6-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="e61c6-116">Algorytm Grovera pyta, czy element na liście jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="e61c6-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="e61c6-117">Odbywa się to przez utworzenie superpozycji indeksów listy z poszczególnymi współczynnikami (amplitudy prawdopodobieństwa) reprezentującej prawdopodobieństwo tego, że określony indeks jest wyszukiwany.</span><span class="sxs-lookup"><span data-stu-id="e61c6-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="e61c6-118">W algorytmie istnieją dwa kroki, które przyrostowo zwiększają współczynnik szukanego indeksu, do osiągnięcia amplitudy prawdopodobieństwa tego współczynnika równej 1.</span><span class="sxs-lookup"><span data-stu-id="e61c6-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="e61c6-119">Liczba przyrostowych zwiększeń jest mniejsza niż liczba elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="e61c6-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="e61c6-120">Dlatego algorytm wyszukiwania Grovera wykonuje wyszukiwanie w mniejszej liczbie kroków niż klasyczne algorytmy.</span><span class="sxs-lookup"><span data-stu-id="e61c6-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagram funkcjonalny algorytmu wyszukiwania Grovera](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="e61c6-122">Tworzenie kodu</span><span class="sxs-lookup"><span data-stu-id="e61c6-122">Write the code</span></span>

1. <span data-ttu-id="e61c6-123">Za pomocą zestawu Quantum Development Kit [Utwórz nowy Q# projekt dla aplikacji](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="e61c6-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="e61c6-124">Nadaj projektowi tytuł `Grover`.</span><span class="sxs-lookup"><span data-stu-id="e61c6-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="e61c6-125">Dodaj następujący kod do pliku `Program.qs` w nowym projekcie:</span><span class="sxs-lookup"><span data-stu-id="e61c6-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="e61c6-126">Aby zdefiniować przeszukiwaną listę, utwórz nowy plik `Reflections.qs` i wklej następujący kod:</span><span class="sxs-lookup"><span data-stu-id="e61c6-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="e61c6-127">Operacja `ReflectAboutMarked` definiuje oznaczone dane wejściowe, które są wyszukiwane: ciąg naprzemiennych wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="e61c6-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="e61c6-128">W tym przykładzie oznaczone dane wejściowe są na stałe umieszczone w kodzie. Przykład można rozszerzyć, aby wyszukać różne dane wejściowe, lub uogólnić, aby wyszukać dowolne dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="e61c6-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="e61c6-129">Następnie uruchom nowy program, Q# Aby znaleźć element oznaczony przez `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="e61c6-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="e61c6-130">Q# aplikacje z programem Visual Studio lub Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e61c6-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="e61c6-131">Plik wykonywalny uruchomi operację lub funkcję oznaczoną atrybutem `@EntryPoint()` w symulatorze lub estymatorze zasobów, w zależności od konfiguracji projektu i opcji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="e61c6-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="e61c6-132">W programie Visual Studio wystarczy nacisnąć klawisze Ctrl + F5, aby wykonać skrypt.</span><span class="sxs-lookup"><span data-stu-id="e61c6-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="e61c6-133">W programie VS Code za pierwszym razem skompiluj plik `Program.qs`, wpisując w terminalu następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="e61c6-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="e61c6-134">Przy kolejnych uruchomieniach nie musisz ponownie kompilować pliku.</span><span class="sxs-lookup"><span data-stu-id="e61c6-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="e61c6-135">Aby go uruchomić, wprowadź następujące polecenie i naciśnij klawisz Enter:</span><span class="sxs-lookup"><span data-stu-id="e61c6-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="e61c6-136">W terminalu powinien zostać wyświetlony następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="e61c6-136">You should see the following message displayed in the terminal:</span></span>

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

<span data-ttu-id="e61c6-137">Dzieje się tak, ponieważ nie określono liczby kubitów do użycia, a więc w terminalu wyświetlane są polecenia dostępne na potrzeby pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="e61c6-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="e61c6-138">Jeśli chcesz użyć 5 kubitów, wpisz:</span><span class="sxs-lookup"><span data-stu-id="e61c6-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="e61c6-139">Po naciśnięciu klawisza Enter powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e61c6-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="e61c6-140">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e61c6-140">Next steps</span></span>

<span data-ttu-id="e61c6-141">W przypadku korzystania z tego samouczka zapoznaj się z poniższymi zasobami, aby dowiedzieć się więcej na temat tworzenia Q# własnych aplikacji Quantum:</span><span class="sxs-lookup"><span data-stu-id="e61c6-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="e61c6-142">Wróć do przewodnika Wprowadzenie do zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="e61c6-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="e61c6-143">Wypróbuj bardziej ogólny [przykład](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) algorytmu wyszukiwania Grover</span><span class="sxs-lookup"><span data-stu-id="e61c6-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="e61c6-144">Dowiedz się więcej o wyszukiwaniu Grovera z artykułów Quantum Kata</span><span class="sxs-lookup"><span data-stu-id="e61c6-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="e61c6-145">Przeczytaj więcej o [wzmacnianiu amplitudy][amplitude-amplification] — technice obliczeń kwantowych, na której bazuje algorytm wyszukiwania Grovera</span><span class="sxs-lookup"><span data-stu-id="e61c6-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="e61c6-146">Pojęcia związane z obliczeniami kwantowymi</span><span class="sxs-lookup"><span data-stu-id="e61c6-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="e61c6-147">Przykłady zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="e61c6-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
