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
ms.openlocfilehash: 1110f32a6486de1a346b115fa928a098749b6690
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866880"
---
# <a name="improving-documentation"></a><span data-ttu-id="f6c98-103">Ulepszanie dokumentacji</span><span class="sxs-lookup"><span data-stu-id="f6c98-103">Improving Documentation</span></span>

<span data-ttu-id="f6c98-104">Dokumentacja zestawu Quantum Development Kit obejmuje kilka różnych formularzy, takich jak informacje są łatwo dostępne dla deweloperów Quantum.</span><span class="sxs-lookup"><span data-stu-id="f6c98-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="f6c98-105">Zgodnie z zasadami dokumentacji [jako kod](https://www.writethedocs.org/guide/docs-as-code/)cała dokumentacja zestawu SDK Development Kit jest formatowana jako kod i jest zarządzana przy użyciu narzędzia Git w taki sam sposób jak kod źródłowy, który jest używany do tworzenia zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f6c98-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="f6c98-106">W większości przypadków dokumentacja dotycząca kodu zawiera różne formy [promocji](https://daringfireball.net/projects/markdown/), czyli język pisania sformatowanego tekstu w formacie zwykłego tekstu, który jest łatwy do użycia w wierszu polecenia, w środowisk IDE i z kontrolą źródła.</span><span class="sxs-lookup"><span data-stu-id="f6c98-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="f6c98-107">Podobnie przyjmujemy bibliotekę [MathJax](https://www.mathjax.org/) , aby umożliwić formatowanie matematyczne w dokumentacji przy użyciu języka lateksowego, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="f6c98-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="f6c98-108">W ten sposób każda forma dokumentacji różni się nieco w zależności od szczegółów:</span><span class="sxs-lookup"><span data-stu-id="f6c98-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="f6c98-109">**Dokumentacja dotycząca pojęć** składa się z zestawu artykułów opublikowanych w https://docs.microsoft.com/quantum programie i opisujących wszystkie informacje od podstaw obliczeń opartych na usłudze Quantum do specyfikacji technicznych dla formatów wymiany.</span><span class="sxs-lookup"><span data-stu-id="f6c98-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="f6c98-110">Te artykuły są zapisywane w [DocFXej promocji (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), która jest używana do tworzenia rozbudowanych zestawów dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="f6c98-111">**Dokumentacja interfejsu API** to zestaw stron dla każdej Q# funkcji, operacji i typu zdefiniowanego przez użytkownika, który jest publikowany w https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="f6c98-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="f6c98-112">Te strony dokumentują dane wejściowe i operacje do każdego z nich, a także przykłady i linki do dodatkowych informacji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="f6c98-113">Dokumentacja interfejsu API jest automatycznie wyodrębniana z małych dokumentów DFM w Q# kodzie źródłowym jako część każdej wersji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="f6c98-114">Pliki **README <!----> . MD** dołączone do każdego przykładu i Kata opisują sposób użycia tego przykładu lub Kata są używane, co obejmuje i w jaki sposób odnosi się do reszty zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f6c98-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="f6c98-115">Te pliki są zapisywane przy użyciu [promocji (GFM) usługi GitHub](https://github.github.com/gfm/), która jest bardziej lekkim rozwiązaniem alternatywnym dla dołączania dokumentacji bezpośrednio do repozytoriów kodu.</span><span class="sxs-lookup"><span data-stu-id="f6c98-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="f6c98-116">Współtworzenie dokumentacji koncepcyjnej</span><span class="sxs-lookup"><span data-stu-id="f6c98-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="f6c98-117">Aby przyczynić się do usprawnienia dokumentacji koncepcyjnej lub Readme, rozpoczyna się od żądania ściągnięcia do [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)lub [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="f6c98-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="f6c98-118">Opiszemy więcej informacji na temat żądań ściągnięcia poniżej, ale teraz istnieje kilka rzeczy, które warto wziąć pod uwagę podczas ulepszania dokumentacji:</span><span class="sxs-lookup"><span data-stu-id="f6c98-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="f6c98-119">Czytelnicy pochodzą z dokumentacji zestawu Quantum Development Kit z bardzo szerokiego zakresu teł.</span><span class="sxs-lookup"><span data-stu-id="f6c98-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="f6c98-120">Wszyscy studenci z dużą szkołą, którzy chcą poznać coś nowego i atrakcyjnego przez nauczyciela z wykorzystaniem analiz Quantum, powinni mieć możliwość uzyskania czegoś z dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="f6c98-121">W zakresie, w jakim jest to możliwe, nie przyjmij szerszej wiedzy na temat tych czytelników, ponieważ mogą one dopiero się rozpoczynać. Jest ona najbardziej przydatna, jeśli można podać jasne i dostępne opisy lub udostępnić linki do innych zasobów, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="f6c98-122">Zestawy dokumentacji nie są inaczej, jak książki lub dokumenty, w których czytelnicy mogą się pojawić, co może wyglądać jak "środek".</span><span class="sxs-lookup"><span data-stu-id="f6c98-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="f6c98-123">Na przykład aparaty wyszukiwania mogą nie zasugerować indeksu lub mogły zostać wysłane przez znajomego próbującego Ci pomóc. Spróbuj, aby pomóc czytelnikowi, zawsze dostarczając jasno kontekst i linki tam, gdzie jest to odpowiednie.</span><span class="sxs-lookup"><span data-stu-id="f6c98-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="f6c98-124">Niektórzy czytelnicy zobaczą, że abstrakcyjne instrukcje i definicje są najbardziej przydatne, a inne czytelnicy działają najlepiej przez ekstrapolację z konkretnych przykładów.</span><span class="sxs-lookup"><span data-stu-id="f6c98-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="f6c98-125">Udostępnienie zarówno ogólnego przypadku, jak i konkretnych przykładów może pomóc obu czytelnikom w największej liczbie programów związanych z programowaniem Quantum.</span><span class="sxs-lookup"><span data-stu-id="f6c98-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="f6c98-126">Szczególnie jeśli zapisałeś również kod, który jest udokumentowany, elementy mogą być oczywiste, które nie są widoczne dla czytnika.</span><span class="sxs-lookup"><span data-stu-id="f6c98-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="f6c98-127">Nie ma żadnego unikatowego najlepszego sposobu programowania, więc niezależnie od tego, jak sprytne lub doświadczony czytelnik nie może się przydać, nie mogą oni odgadnąć od tego, jakie wzorce projektowe okazały się najbardziej pomocne do wyrażania pomysłów w kodzie.</span><span class="sxs-lookup"><span data-stu-id="f6c98-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="f6c98-128">Czyszczenie informacji o tym, jak czytelnik może oczekiwać na użycie kodu, może pomóc w udostępnieniu tego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="f6c98-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="f6c98-129">Wielu członków społeczności programowania Quantum to badacze akademickie i są rozpoznawane głównie przez cytaty dla ich wkładu do społeczności.</span><span class="sxs-lookup"><span data-stu-id="f6c98-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="f6c98-130">Oprócz ułatwienia czytelnikom znajdowania dodatkowych materiałów, dzięki czemu warto prawidłowo zamieszczać dane naukowe, takie jak dokumenty, rozmowy, wpisy w blogu i narzędzia programowe, mogą pomóc akademickim współautorom w prowadzeniu najlepszych zadań do ulepszania społeczności.</span><span class="sxs-lookup"><span data-stu-id="f6c98-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="f6c98-131">Społeczność programowania Quantum jest szeroką i bardzo różnorodną społecznością.</span><span class="sxs-lookup"><span data-stu-id="f6c98-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="f6c98-132">Korzystanie z teoretycznych rzeczowników w przykładach innych osób (np.: "Jeśli użytkownik..., będzie..."), może przełączać się, a nie uwzględnić.</span><span class="sxs-lookup"><span data-stu-id="f6c98-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="f6c98-133">Firma Cognizant nazwiska osób w cytatach i łączach, a poprawna dołączenie znaków nienależących do zestawu ASCII może zapewnić różnorodność społeczności, wskazując jej składowe.</span><span class="sxs-lookup"><span data-stu-id="f6c98-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="f6c98-134">Podobnie wiele wyrazów w języku angielskim jest często używanych w hateful, w taki sposób, że ich użycie w dokumentacji technicznej może spowodować szkody zarówno dla indywidualnych czytelników, jak i dla społeczności.</span><span class="sxs-lookup"><span data-stu-id="f6c98-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="f6c98-135">Odwołuje się do przykładowego kodu z artykułu koncepcyjnego</span><span class="sxs-lookup"><span data-stu-id="f6c98-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="f6c98-136">Jeśli chcesz dołączyć kod z [repozytorium przykładów](https://github.com/Microsoft/Quantum), możesz to zrobić przy użyciu specjalnego DocFXej promocji z nieprawidłowymi wersjami:</span><span class="sxs-lookup"><span data-stu-id="f6c98-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="f6c98-137">To polecenie spowoduje zaimportowanie wierszy 4 do 8 [ `Game.qs` pliku z `chsh-game` przykładu](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs)i oznaczenie ich jako Q# kodu na potrzeby wyróżniania składni.</span><span class="sxs-lookup"><span data-stu-id="f6c98-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="f6c98-138">Za pomocą tego polecenia można uniknąć duplikowania kodu między artykułami koncepcyjnymi i repozytorium przykładów, aby kod przykładowy w dokumentacji był zawsze aktualny, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="f6c98-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="f6c98-139">Współtworzenie odwołań do interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f6c98-139">Contributing to the API References</span></span>

<span data-ttu-id="f6c98-140">Aby współtworzyć udoskonalenia odwołań do interfejsów API, warto otworzyć żądanie ściągnięcia bezpośrednio na udokumentowanym kodzie.</span><span class="sxs-lookup"><span data-stu-id="f6c98-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="f6c98-141">Każda funkcja, operacja lub typ zdefiniowany przez użytkownika obsługuje komentarz do dokumentacji (jest to znak `///` zamiast `//` ).</span><span class="sxs-lookup"><span data-stu-id="f6c98-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="f6c98-142">Podczas kompilowania każdej wersji zestawu Quantum Development Kit te komentarze są używane do generowania odniesienia do interfejsu API w https://docs.microsoft.com/qsharp/api/ , w tym szczegółowych informacji o danych wejściowych i wyjść z każdego z nich, założeń, każdy możliwy do przetworzenia i przykłady ich użycia.</span><span class="sxs-lookup"><span data-stu-id="f6c98-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6c98-143">Pamiętaj, aby nie edytować ręcznie wygenerowanej dokumentacji interfejsu API, ponieważ te pliki są zastępowane w każdej nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="f6c98-144">Firma Microsoft zastrzega sobie udział w społeczności i chce mieć pewność, że zmiany będą nadal pomocne w udostępnieniu ich przez program.</span><span class="sxs-lookup"><span data-stu-id="f6c98-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="f6c98-145">Rozważmy na przykład funkcję `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="f6c98-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="f6c98-146">Komentarz dokumentacji powinien pomóc użytkownikowi dowiedzieć się, jak interpretować `bits` i jak `oracle` i do czego służy funkcja.</span><span class="sxs-lookup"><span data-stu-id="f6c98-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="f6c98-147">Każdą z tych informacji można dostarczyć do Q# kompilatora przez specjalną sekcję o nazwie promocji w komentarzu do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="f6c98-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="f6c98-148">Przykładowo `ControlledOnBitString` możemy napisać coś w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f6c98-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

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

<span data-ttu-id="f6c98-149">Możesz zobaczyć wyrenderowaną wersję kodu powyżej w [dokumentacji interfejsu API dla `ControlledOnBitString` funkcji](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="f6c98-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="f6c98-150">Oprócz ogólnych metod pisania dokumentacji, w opisie komentarzy dokumentacji interfejsu API pomocne jest zachowanie kilku rzeczy:</span><span class="sxs-lookup"><span data-stu-id="f6c98-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="f6c98-151">Format każdego komentarza dokumentacji musi być zgodny z Q# oczekiwaniami kompilatora, aby dokumentacja była poprawnie wyświetlana.</span><span class="sxs-lookup"><span data-stu-id="f6c98-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="f6c98-152">Niektóre sekcje, takie jak `/// # Remarks` Zezwalaj na zawartość dowolnego kształtu, natomiast sekcje takie jak `/// # See Also` sekcja są bardziej restrykcyjne.</span><span class="sxs-lookup"><span data-stu-id="f6c98-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="f6c98-153">Czytelnik może odczytać dokumentację interfejsu API w głównej witrynie odniesienia interfejsu API, na podsumowanie dla każdej przestrzeni nazw, a nawet w środowisku IDE za pomocą informacji o aktywowaniu.</span><span class="sxs-lookup"><span data-stu-id="f6c98-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="f6c98-154">Upewnienie się, że `/// # Summary` nie jest dłużej niż w przypadku zdania, ułatwia czytelnikowi szybkie sortowanie, czy muszą one zostać odczytane w innym miejscu i może pomóc w szybkim skanowaniu za pomocą podsumowań przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="f6c98-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="f6c98-155">Dokumentacja może być również w pełni zawracać do samego kodu, ale jest to prawidłowe!</span><span class="sxs-lookup"><span data-stu-id="f6c98-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="f6c98-156">Nawet niewielki fragment kodu może mieć nieoczekiwane skutki dla użytkowników, którzy nie znają kontekstu, w którym ten kod istnieje.</span><span class="sxs-lookup"><span data-stu-id="f6c98-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="f6c98-157">Dostarczając konkretne przykłady i jasne wyjaśnienia, możesz pomóc użytkownikom w najlepszym użyciu dostępnego dla nich kodu.</span><span class="sxs-lookup"><span data-stu-id="f6c98-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
