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
# <a name="improving-documentation"></a><span data-ttu-id="2f75c-103">Ulepszanie dokumentacji</span><span class="sxs-lookup"><span data-stu-id="2f75c-103">Improving Documentation</span></span> #

<span data-ttu-id="2f75c-104">Dokumentacja zestawu Quantum Development Kit obejmuje kilka różnych formularzy, takich jak informacje są łatwo dostępne dla deweloperów Quantum.</span><span class="sxs-lookup"><span data-stu-id="2f75c-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="2f75c-105">Zgodnie z zasadami dokumentacji [jako kod](https://www.writethedocs.org/guide/docs-as-code/)cała dokumentacja zestawu SDK Development Kit jest formatowana jako kod i jest zarządzana przy użyciu narzędzia Git w taki sam sposób jak kod źródłowy, który jest używany do tworzenia zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="2f75c-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="2f75c-106">W większości przypadków dokumentacja dotycząca kodu zawiera różne formy [promocji](https://daringfireball.net/projects/markdown/), czyli język pisania sformatowanego tekstu w formacie zwykłego tekstu, który jest łatwy do użycia w wierszu polecenia, w środowisk IDE i z kontrolą źródła.</span><span class="sxs-lookup"><span data-stu-id="2f75c-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="2f75c-107">Podobnie przyjmujemy bibliotekę [MathJax](https://www.mathjax.org/) , aby umożliwić formatowanie matematyczne w dokumentacji przy użyciu języka lateksowego, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="2f75c-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="2f75c-108">W ten sposób każda forma dokumentacji różni się nieco w zależności od szczegółów:</span><span class="sxs-lookup"><span data-stu-id="2f75c-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="2f75c-109">**Dokumentacja dotycząca pojęć** składa się z zestawu artykułów, które są publikowane w https://docs.microsoft.com/quantum i opisują wszystko, od podstaw obliczeniowych usługi Quantum do specyfikacji technicznych dla formatów wymiany.</span><span class="sxs-lookup"><span data-stu-id="2f75c-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="2f75c-110">Te artykuły są zapisywane w [DocFXej promocji (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), która jest używana do tworzenia rozbudowanych zestawów dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="2f75c-111">**Dokumentacja interfejsu API** to zestaw stron dla każdej funkcji Q #, operacji i typu zdefiniowanego przez użytkownika, który jest publikowany w https://docs.microsoft.com/qsharp/api/.</span><span class="sxs-lookup"><span data-stu-id="2f75c-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="2f75c-112">Te strony dokumentują dane wejściowe i operacje do każdego z nich, a także przykłady i linki do dodatkowych informacji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="2f75c-113">Odwołanie do interfejsu API jest automatycznie wyodrębniane z małych dokumentów DFM w kodzie kodu źródłowego Q # jako część każdej wersji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="2f75c-114">Pliki **readme<!---->. MD** dołączone do każdego przykładu i Kata opisują, jak używać tego przykładu lub Kata jest używany, co obejmuje, i w jaki sposób odnosi się do reszty zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="2f75c-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="2f75c-115">Te pliki są zapisywane przy użyciu [promocji (GFM) usługi GitHub](https://github.github.com/gfm/), która jest bardziej lekkim rozwiązaniem alternatywnym dla dołączania dokumentacji bezpośrednio do repozytoriów kodu.</span><span class="sxs-lookup"><span data-stu-id="2f75c-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="2f75c-116">Współtworzenie dokumentacji koncepcyjnej</span><span class="sxs-lookup"><span data-stu-id="2f75c-116">Contributing to the Conceptual Documentation</span></span> ##

<span data-ttu-id="2f75c-117">Aby przyczynić się do usprawnienia dokumentacji koncepcyjnej lub Readme, rozpoczyna się od żądania ściągnięcia do [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)lub [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="2f75c-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="2f75c-118">Opiszemy więcej informacji na temat żądań ściągnięcia poniżej, ale teraz istnieje kilka rzeczy, które warto wziąć pod uwagę podczas ulepszania dokumentacji:</span><span class="sxs-lookup"><span data-stu-id="2f75c-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="2f75c-119">Czytelnicy pochodzą z dokumentacji zestawu Quantum Development Kit z bardzo szerokiego zakresu teł.</span><span class="sxs-lookup"><span data-stu-id="2f75c-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="2f75c-120">Wszyscy studenci z dużą szkołą, którzy chcą poznać coś nowego i atrakcyjnego przez nauczyciela z wykorzystaniem analiz Quantum, powinni mieć możliwość uzyskania czegoś z dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="2f75c-121">W zakresie, w jakim jest to możliwe, nie przyjmij szerszej wiedzy na temat tych czytelników, ponieważ mogą one dopiero się rozpoczynać. Jest ona najbardziej przydatna, jeśli można podać jasne i dostępne opisy lub udostępnić linki do innych zasobów, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="2f75c-122">Zestawy dokumentacji nie są inaczej, jak książki lub dokumenty, w których czytelnicy mogą się pojawić, co może wyglądać jak "środek".</span><span class="sxs-lookup"><span data-stu-id="2f75c-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="2f75c-123">Na przykład aparaty wyszukiwania mogą nie zasugerować indeksu lub mogły zostać wysłane przez znajomego próbującego Ci pomóc. Spróbuj, aby pomóc czytelnikowi, zawsze dostarczając jasno kontekst i linki tam, gdzie jest to odpowiednie.</span><span class="sxs-lookup"><span data-stu-id="2f75c-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="2f75c-124">Niektórzy czytelnicy zobaczą, że abstrakcyjne instrukcje i definicje są najbardziej przydatne, a inne czytelnicy działają najlepiej przez ekstrapolację z konkretnych przykładów.</span><span class="sxs-lookup"><span data-stu-id="2f75c-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="2f75c-125">Udostępnienie zarówno ogólnego przypadku, jak i konkretnych przykładów może pomóc obu czytelnikom w największej liczbie programów związanych z programowaniem Quantum.</span><span class="sxs-lookup"><span data-stu-id="2f75c-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="2f75c-126">Szczególnie jeśli zapisałeś również kod, który jest udokumentowany, elementy mogą być oczywiste, które nie są widoczne dla czytnika.</span><span class="sxs-lookup"><span data-stu-id="2f75c-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="2f75c-127">Nie ma żadnego unikatowego najlepszego sposobu programowania, więc niezależnie od tego, jak sprytne lub doświadczony czytelnik nie może się przydać, nie mogą oni odgadnąć od tego, jakie wzorce projektowe okazały się najbardziej pomocne do wyrażania pomysłów w kodzie.</span><span class="sxs-lookup"><span data-stu-id="2f75c-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="2f75c-128">Czyszczenie informacji o tym, jak czytelnik może oczekiwać na użycie kodu, może pomóc w udostępnieniu tego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="2f75c-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="2f75c-129">Wielu członków społeczności programowania Quantum to badacze akademickie i są rozpoznawane głównie przez cytaty dla ich wkładu do społeczności.</span><span class="sxs-lookup"><span data-stu-id="2f75c-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="2f75c-130">Oprócz ułatwienia czytelnikom znajdowania dodatkowych materiałów, dzięki czemu warto prawidłowo zamieszczać dane naukowe, takie jak dokumenty, rozmowy, wpisy w blogu i narzędzia programowe, mogą pomóc akademickim współautorom w prowadzeniu najlepszych zadań do ulepszania społeczności.</span><span class="sxs-lookup"><span data-stu-id="2f75c-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="2f75c-131">Społeczność programowania Quantum jest szeroką i bardzo różnorodną społecznością.</span><span class="sxs-lookup"><span data-stu-id="2f75c-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="2f75c-132">Korzystanie z teoretycznych rzeczowników w przykładach innych osób (np.: "Jeśli użytkownik..., będzie..."), może przełączać się, a nie uwzględnić.</span><span class="sxs-lookup"><span data-stu-id="2f75c-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="2f75c-133">Firma Cognizant nazwiska osób w cytatach i łączach, a poprawna dołączenie znaków nienależących do zestawu ASCII może zapewnić różnorodność społeczności, wskazując jej składowe.</span><span class="sxs-lookup"><span data-stu-id="2f75c-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="2f75c-134">Podobnie wiele wyrazów w języku angielskim jest często używanych w hateful, w taki sposób, że ich użycie w dokumentacji technicznej może spowodować szkody zarówno dla indywidualnych czytelników, jak i dla społeczności.</span><span class="sxs-lookup"><span data-stu-id="2f75c-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="2f75c-135">Współtworzenie odwołań do interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2f75c-135">Contributing to the API References</span></span> ##

<span data-ttu-id="2f75c-136">Aby współtworzyć udoskonalenia odwołań do interfejsów API, warto otworzyć żądanie ściągnięcia bezpośrednio na udokumentowanym kodzie.</span><span class="sxs-lookup"><span data-stu-id="2f75c-136">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="2f75c-137">Każda funkcja, operacja lub typ zdefiniowany przez użytkownika obsługuje komentarz do dokumentacji (oznaczone `///` zamiast `//`).</span><span class="sxs-lookup"><span data-stu-id="2f75c-137">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="2f75c-138">Podczas kompilowania każdej wersji zestawu Quantum Development Kit te komentarze są używane do generowania odniesienia do interfejsu API w https://docs.microsoft.com/qsharp/api/ , w tym szczegółów dotyczących danych wejściowych i wyjściowych z każdego z nich, założeń, każdy możliwy do przetworzenia i przykłady ich użycia.</span><span class="sxs-lookup"><span data-stu-id="2f75c-138">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f75c-139">Pamiętaj, aby nie edytować ręcznie wygenerowanej dokumentacji interfejsu API, ponieważ te pliki są zastępowane w każdej nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-139">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="2f75c-140">Firma Microsoft zastrzega sobie udział w społeczności i chce mieć pewność, że zmiany będą nadal pomocne w udostępnieniu ich przez program.</span><span class="sxs-lookup"><span data-stu-id="2f75c-140">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="2f75c-141">Rozważmy na przykład operację `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.</span><span class="sxs-lookup"><span data-stu-id="2f75c-141">For example, consider an operation `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.</span></span>
<span data-ttu-id="2f75c-142">Komentarz dokumentacji powinien pomóc użytkownikowi dowiedzieć się, jak interpretować `angles`, jakie operacje założono na początkowy stan `register`, jaki ma wpływ na `register` i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="2f75c-142">A documentation comment should help a user learn how to interpret `angles`, what the operation assumes about the initial state of `register`, what the effect on `register` is, and so forth.</span></span>
<span data-ttu-id="2f75c-143">Każdą z tych informacji można dostarczyć do kompilatora Q # przez specjalną sekcję o nazwie promocji w komentarzu do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="2f75c-143">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="2f75c-144">Na przykład `PrepareTrialState`można napisać coś w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="2f75c-144">For the example of `PrepareTrialState`, we might write something like the following:</span></span>

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

<span data-ttu-id="2f75c-145">Oprócz ogólnych metod pisania dokumentacji, w opisie komentarzy dokumentacji interfejsu API pomocne jest zachowanie kilku rzeczy:</span><span class="sxs-lookup"><span data-stu-id="2f75c-145">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="2f75c-146">Format każdego komentarza do dokumentacji musi być zgodny z tym, co kompilator Q # oczekuje, że dokumentacja będzie poprawnie wyświetlana.</span><span class="sxs-lookup"><span data-stu-id="2f75c-146">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="2f75c-147">Niektóre sekcje, takie jak `/// # Remarks` umożliwiają dostęp do zawartości dowolnego kształtu, podczas gdy sekcje, takie jak sekcja `/// # See Also`, są bardziej restrykcyjne.</span><span class="sxs-lookup"><span data-stu-id="2f75c-147">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="2f75c-148">Czytelnik może odczytać dokumentację interfejsu API w głównej witrynie odniesienia interfejsu API, na podsumowanie dla każdej przestrzeni nazw, a nawet w środowisku IDE za pomocą informacji o aktywowaniu.</span><span class="sxs-lookup"><span data-stu-id="2f75c-148">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="2f75c-149">Upewnij się, że `/// # Summary` nie jest dłuższa niż w przypadku zdania, że czytelnik szybko sortuje informacje, czy muszą czytać się dalej lub szukać w innym miejscu i może pomóc w szybkim skanowaniu za pomocą podsumowań przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2f75c-149">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="2f75c-150">Dokumentacja może być również w pełni zawracać do samego kodu, ale jest to prawidłowe!</span><span class="sxs-lookup"><span data-stu-id="2f75c-150">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="2f75c-151">Nawet niewielki fragment kodu może mieć nieoczekiwane skutki dla użytkowników, którzy nie znają kontekstu, w którym ten kod istnieje.</span><span class="sxs-lookup"><span data-stu-id="2f75c-151">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="2f75c-152">Dostarczając konkretne przykłady i jasne wyjaśnienia, możesz pomóc użytkownikom w najlepszym użyciu dostępnego dla nich kodu.</span><span class="sxs-lookup"><span data-stu-id="2f75c-152">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->