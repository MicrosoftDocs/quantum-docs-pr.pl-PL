---
title: Wkładowanie próbek do programu Microsoft QDKe
description: Dowiedz się, jak współtworzyć przykładowy kod w Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024155"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="65b7d-103">Wkładowanie próbek do zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="65b7d-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="65b7d-104">Jeśli interesujesz się współtworzeniem kodu do [repozytorium przykładów](https://github.com/Microsoft/Quantum), Dziękujemy za przeprowadzenie społeczności rozwoju Quantum w lepszym miejscu.</span><span class="sxs-lookup"><span data-stu-id="65b7d-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="65b7d-105">Przykładowe repozytorium zestawu Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="65b7d-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="65b7d-106">Aby pomóc Ci w przygotowaniu Twojego wkładu do uzyskania możliwie największej ilości danych, warto szybko zapoznać się z sposobem tworzenia repozytorium przykładów:</span><span class="sxs-lookup"><span data-stu-id="65b7d-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="65b7d-107">Oznacza to, że próbki w [repozytorium Microsoft/Quantum](https://github.com/microsoft/Quantum) są podzielone według obszaru podmiotu w różne foldery, takie jak `algorithms/`, `arithmetic/`lub `characterization/`.</span><span class="sxs-lookup"><span data-stu-id="65b7d-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="65b7d-108">W folderze dla każdego obszaru tematu każdy przykład składa się z pojedynczego folderu, który zbiera wszystko, co użytkownik musi eksplorować i korzystać z tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="65b7d-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="65b7d-109">Jak przykłady są strukturalne</span><span class="sxs-lookup"><span data-stu-id="65b7d-109">How Samples are Structured</span></span>

<span data-ttu-id="65b7d-110">Przeglądając pliki wchodzące w skład każdego folderu, przyjrzyjmy się [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) przykładowi.</span><span class="sxs-lookup"><span data-stu-id="65b7d-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="65b7d-111">Plik</span><span class="sxs-lookup"><span data-stu-id="65b7d-111">File</span></span>              | <span data-ttu-id="65b7d-112">Opis</span><span class="sxs-lookup"><span data-stu-id="65b7d-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="65b7d-113">Q # projekt używany do kompilowania próbki przy użyciu zestaw .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="65b7d-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="65b7d-114">Operacje i funkcje Q # dla przykładu</span><span class="sxs-lookup"><span data-stu-id="65b7d-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="65b7d-115">C#Program hosta używany do uruchomienia przykładu</span><span class="sxs-lookup"><span data-stu-id="65b7d-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="65b7d-116">Program hosta języka Python używany do uruchomienia przykładu</span><span class="sxs-lookup"><span data-stu-id="65b7d-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="65b7d-117">Dokumentacja na temat tego, co robi przykład i jak z niego korzystać</span><span class="sxs-lookup"><span data-stu-id="65b7d-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="65b7d-118">Nie wszystkie próbki będą mieć dokładnie ten sam zestaw plików (np.: Niektóre przykłady mogą C#nie mieć hosta Python lub niektóre przykłady mogą wymagać Auxillary plików danych).</span><span class="sxs-lookup"><span data-stu-id="65b7d-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="65b7d-119">Anatomia przydatnego pliku Readme</span><span class="sxs-lookup"><span data-stu-id="65b7d-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="65b7d-120">Jest to plik `README.md`, co oznacza, że użytkownicy muszą rozpocząć pracę z Twoim przykładem.</span><span class="sxs-lookup"><span data-stu-id="65b7d-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="65b7d-121">Każda `README.md` powinna rozpoczynać się od pewnych metadanych, które ułatwiają znalezienie Twojego wkładu.</span><span class="sxs-lookup"><span data-stu-id="65b7d-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="65b7d-122">Zobacz, jak jest renderowany przykład chsh-Game</span><span class="sxs-lookup"><span data-stu-id="65b7d-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="65b7d-123">Te metadane są dostępne jako [nagłówek YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) , który wskazuje, jakie języki obejmują przykład (zazwyczaj jest to `qsharp`, `csharp`i `python`) i jakie produkty obejmuje przykład (zazwyczaj tylko `qdk`).</span><span class="sxs-lookup"><span data-stu-id="65b7d-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="65b7d-124">Klucz `page_type: sample` w nagłówku jest wymagany dla przykładu, który będzie wyświetlany w docs.microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="65b7d-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="65b7d-125">Podobnie klucze `product` i `language` mają kluczowe znaczenie dla ułatwienia użytkownikom znajdowania i uruchamiania przykładu.</span><span class="sxs-lookup"><span data-stu-id="65b7d-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="65b7d-126">Po wykonaniu tej czynności warto podać krótkie wprowadzenie, które wskazuje na to, co robi nowy przykład:</span><span class="sxs-lookup"><span data-stu-id="65b7d-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="65b7d-127">Użytkownicy Twojego przykładu zapoznają się również z informacjami o tym, co jest potrzebne do ich uruchomienia (np.: czy użytkownicy potrzebują tylko zestawu Quantum Development Kit lub potrzebują dodatkowego oprogramowania, takiego jak Node. js?):</span><span class="sxs-lookup"><span data-stu-id="65b7d-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="65b7d-128">W przypadku wszystkich tych miejsc można poinformować użytkowników, jak uruchomić przykład:</span><span class="sxs-lookup"><span data-stu-id="65b7d-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="65b7d-129">Na koniec warto poinformować użytkowników o tym, co każdy plik w przykładzie robi i gdzie mogą przejść więcej informacji:</span><span class="sxs-lookup"><span data-stu-id="65b7d-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="65b7d-130">Upewnij się, że w tym miejscu Użyj bezwzględnych adresów URL, ponieważ przykład zostanie wyświetlony pod innym adresem URL, gdy jest renderowany w docs.microsoft.com/samples!</span><span class="sxs-lookup"><span data-stu-id="65b7d-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
