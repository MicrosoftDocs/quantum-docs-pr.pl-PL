---
title: Współtworzenie kodu do programu Microsoft QDKe
description: Dowiedz się, jak współtworzyć kod przykładowy i bibliotekę w Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 956b0957a5261b8a77bf18d776fbcc2853bfbfe7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866913"
---
# <a name="contributing-code"></a><span data-ttu-id="6b7d1-103">Zasady współtworzenia</span><span class="sxs-lookup"><span data-stu-id="6b7d1-103">Contributing Code</span></span>

<span data-ttu-id="6b7d1-104">Oprócz zgłaszania problemów i ulepszania dokumentacji, współdziałanie kodu z zestawem SDK Development Kit może być bardzo bezpośrednim sposobem, aby pomóc swoim partnerom w społeczności programowania Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="6b7d1-105">Dzięki objęcie kodu możesz pomóc w rozwiązywaniu problemów, dostarczeniu nowych przykładów, Ułatw korzystanie z istniejących bibliotek, a nawet dodawać zupełnie nowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="6b7d1-106">W tym przewodniku zawarto szczegółowe informacje o tym, czego szukamy, gdy sprawdzimy żądania ściągnięcia, aby pomóc Ci w Twoim udostępnieniu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="6b7d1-107">Czego szukamy</span><span class="sxs-lookup"><span data-stu-id="6b7d1-107">What We Look For</span></span>

<span data-ttu-id="6b7d1-108">Idealny udział w kodzie kompiluje się w istniejącej pracy w repozytorium Quantum Development Kit, aby rozwiązać problemy, rozwinąć istniejące funkcje lub dodać nowe funkcje, które znajdują się w zakresie repozytorium.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="6b7d1-109">Gdy akceptujemy wkład kodu, jest on częścią zestawu Quantum Development Kit, w taki sposób, że nowe funkcje zostaną wydane, utrzymane i opracowane w taki sam sposób jak w pozostałej części zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="6b7d1-110">W ten sposób jest przydatne, gdy funkcje dodane przez wkład są dobrze przetestowane i są udokumentowane.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="6b7d1-111">Testy jednostkowe</span><span class="sxs-lookup"><span data-stu-id="6b7d1-111">Unit Tests</span></span>

<span data-ttu-id="6b7d1-112">Q#Funkcje, operacje i typy zdefiniowane przez użytkownika, które tworzą biblioteki, takie jak Canon, są automatycznie testowane jako część opracowywania w repozytorium [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="6b7d1-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="6b7d1-113">Gdy zostanie otwarte nowe żądanie ściągnięcia, na przykład nasza konfiguracja [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) sprawdzi, czy zmiany w żądaniu ściągnięcia nie podzielą żadnych istniejących funkcji, od których zależy społeczność programowania Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="6b7d1-114">W najnowszej Q# wersji test jednostkowy jest definiowany przy użyciu `@Test("QuantumSimulator")` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="6b7d1-115">Argument może mieć wartość "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" lub dowolną w pełni kwalifikowaną nazwę określającą cel wykonania.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="6b7d1-116">Kilka atrybutów definiujących różne elementy docelowe wykonywania może być dołączanych do tego samego możliwego do odtworzenia.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="6b7d1-117">Niektóre z naszych testów nadal używają przestarzałego pakietu [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , który uwidacznia wszystkie Q# funkcje i operacje kończące `Test` się na platformie [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="6b7d1-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="6b7d1-118">Ten pakiet nie jest już wymagany do definiowania testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="6b7d1-119">Poniższa funkcja służy do upewnienia się, <xref:microsoft.quantum.canon.fst> że <xref:microsoft.quantum.canon.snd> funkcje i zwracają odpowiednie dane wyjściowe w reprezentatywnym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="6b7d1-120">Jeśli dane wyjściowe `Fst` lub `Snd` są nieprawidłowe, `fail` instrukcja jest używana, aby spowodować niepowodzenie testu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

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

<span data-ttu-id="6b7d1-121">Bardziej skomplikowane warunki można sprawdzić przy użyciu technik w [sekcji Testowanie](xref:microsoft.quantum.libraries.diagnostics) w przewodniku biblioteki standardowe.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="6b7d1-122">Na przykład następujące testy sprawdzają, czy `H(q); X(q); H(q);` jako wywołane przez <xref:microsoft.quantum.canon.applywith> są takie same jak `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="6b7d1-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="6b7d1-123">Przy dodawaniu nowych funkcji warto również dodać nowe testy, aby upewnić się, że Twój udział ma odpowiednie znaczenie.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="6b7d1-124">Pomaga to w pozostałej części społeczności do obsługi i opracowywania funkcji, a w szczególności pomaga innym deweloperom wiedzieć, że mogą polegać na funkcji.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="6b7d1-125">Działa to również w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-125">This works the other way around, too!</span></span>
> <span data-ttu-id="6b7d1-126">Jeśli istnieje funkcja, w której brakuje niektórych testów, to ułatwia nam Dodawanie pokrycia testów.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="6b7d1-127">Lokalnie testy jednostkowe można uruchomić za pomocą Eksploratora testów programu Visual Studio lub `dotnet test` polecenia, dzięki czemu możesz sprawdzić swój udział przed otwarciem żądania ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="6b7d1-128">Gdy odrzucimy żądanie ściągnięcia</span><span class="sxs-lookup"><span data-stu-id="6b7d1-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="6b7d1-129">Czasami odrzucimy żądanie ściągnięcia dla udziału.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="6b7d1-130">W takim przypadku nie oznacza to, że jest ona zła, ponieważ istnieje kilka powodów, dla których firma Microsoft może nie być w stanie zaakceptować określonego udziału.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="6b7d1-131">Najprawdopodobniej najczęściej, udział w społeczności programowania Quantum to naprawdę dobry, ale repozytoria zestawu Quantum Development Kit nie są właściwym miejscem do jego opracowywania.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="6b7d1-132">W takich przypadkach zdecydowanie zachęcamy do tworzenia własnego repozytorium---częścią siły zestawu SDK Development Kit jest łatwość tworzenia i rozpowszechniania własnych bibliotek przy użyciu usługi GitHub i NuGet.org, tak samo jak w przypadku obecnie dystrybuowania biblioteki Canon i chemii.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="6b7d1-133">W innych przypadkach możemy odrzucić dobry wkład po prostu, ponieważ nie jest to jeszcze gotowe do utrzymania i opracowywania.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="6b7d1-134">Może być trudne do wykonania wszystko, dlatego planujemy, jakie funkcje najlepiej współpracują z planem.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="6b7d1-135">Może to być inny przypadek, gdzie wydawanie funkcji jako biblioteki innej firmy może mieć wiele sensu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="6b7d1-136">Alternatywnie firma Microsoft może poprosił o pomoc w modyfikowaniu funkcji w celu lepszego dopasowania do naszego planu, dzięki czemu możemy z niego korzystać.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="6b7d1-137">Poprosimy również o wprowadzenie zmian w żądaniu ściągnięcia, jeśli wymaga to więcej dokumentacji lub testów jednostkowych, aby pomóc nam w jego użyciu lub jeśli jest ona zależna od stylu od pozostałej części Q# bibliotek, które utrudniają użytkownikom znalezienie funkcji.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="6b7d1-138">W takich przypadkach będziemy próbować zaoferować kilka porad w przeglądach kodu na temat tego, co można dodać lub zmienić, aby ułatwić mu dołączenie.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="6b7d1-139">Na koniec nie można zatwierdzić wkładów, które powodują szkody dla społeczności przetwarzania w usłudze [Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="6b7d1-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="6b7d1-140">Chcemy mieć pewność, że wkłady pełnią rolę całej społeczności obliczeniowej usługi Quantum, zarówno w swojej bieżącej różnorodności, jak i w przyszłości, gdy rośnie, aby jeszcze bardziej włączać.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="6b7d1-141">Dziękujemy za pomoc w realizacji tego celu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b7d1-142">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="6b7d1-142">Next steps</span></span>

<span data-ttu-id="6b7d1-143">Dziękujemy za pomoc w opracowaniu zestawu Quantum Development Kit doskonałego zasobu dla całej społeczności programistycznej usługi Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="6b7d1-144">Aby dowiedzieć się więcej, przejdź do poniższej wskazówki dotyczącej Q# stylu.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b7d1-145">Informacje na temat Q# wytycznych dotyczących stylu</span><span class="sxs-lookup"><span data-stu-id="6b7d1-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="6b7d1-146">W zależności od rodzaju kodu, w którym się wnosisz, może być konieczne dodatkowe zagadnienia, które mogą pomóc Ci zapewnić, że udział będzie tak dobry dla społeczności.</span><span class="sxs-lookup"><span data-stu-id="6b7d1-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b7d1-147">Dowiedz się więcej na temat tworzenia próbek</span><span class="sxs-lookup"><span data-stu-id="6b7d1-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
