---
title: Otwieranie żądań ściągnięcia | Microsoft Docs
description: Otwieranie żądań ściągnięcia
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183730"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="d19bf-103">Otwieranie żądań ściągnięcia</span><span class="sxs-lookup"><span data-stu-id="d19bf-103">Opening Pull Requests</span></span> #

<span data-ttu-id="d19bf-104">Cała dokumentacja zestawu Quantum Development Kit jest zarządzana przy użyciu systemu kontroli wersji Git przy użyciu kilku repozytoriów hostowanych w serwisie GitHub.</span><span class="sxs-lookup"><span data-stu-id="d19bf-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="d19bf-105">Korzystanie z usługi git i usługi GitHub ułatwia współpracę w szerokim zakresie w zestawie Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="d19bf-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="d19bf-106">W szczególności każde repozytorium git może zostać sklonowane lub rozwidlenie w celu przetworzenia całkowicie niezależnej kopii tego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="d19bf-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="d19bf-107">Dzięki temu można pracować nad Twoim udziałem przy użyciu narzędzi i w preferowany tempie.</span><span class="sxs-lookup"><span data-stu-id="d19bf-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="d19bf-108">Gdy wszystko będzie gotowe, możesz wysłać nam żądanie dołączenia Twojego wkładu do naszych repozytoriów, korzystając z funkcji _żądania ściągnięcia_ usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="d19bf-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="d19bf-109">Strona dla każdego żądania ściągnięcia zawiera szczegółowe informacje o wszystkich zmianach, które wprowadzają swój wkład, listę komentarzy dotyczących Twojego wkładu oraz zestaw narzędzi do przeglądu, które mogą być używane przez innych członków społeczności do przekazywania opinii i porad.</span><span class="sxs-lookup"><span data-stu-id="d19bf-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="d19bf-110">Chociaż pełny samouczek dotyczący usługi git wykracza poza zakres tego przewodnika, można zasugerować następujące linki, aby uzyskać więcej zasobów dotyczących uczenia usługi git:</span><span class="sxs-lookup"><span data-stu-id="d19bf-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="d19bf-111">[Poznaj usługę git](https://www.atlassian.com/git): zestaw samouczków usługi git Atlassian.</span><span class="sxs-lookup"><span data-stu-id="d19bf-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="d19bf-112">[Kontrola wersji w Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Przewodnik po użyciu Visual Studio Code jako graficzny interfejs użytkownika dla usługi git.</span><span class="sxs-lookup"><span data-stu-id="d19bf-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="d19bf-113">[Laboratorium uczenia GitHub](https://lab.github.com/): zestaw kursów online do korzystania z usługi git, usługi GitHub i powiązanych technologii.</span><span class="sxs-lookup"><span data-stu-id="d19bf-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="d19bf-114">[Wizualizacja git](https://git-school.github.io/visualizing-git/): interaktywne narzędzie do wizualizacji sposobu zmiany stanu repozytorium przez polecenia usługi git.</span><span class="sxs-lookup"><span data-stu-id="d19bf-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="d19bf-115">[Kontrola wersji za pomocą narzędzia Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): samouczek usługi git ukierunkowany na obliczenia naukowe.</span><span class="sxs-lookup"><span data-stu-id="d19bf-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="d19bf-116">[Informacje o rozgałęzieniu usługi git](https://learngitbranching.js.org/): interaktywny zestaw rozgałęzień i układanki w celu uzyskania pomocy dotyczącej nowych funkcji usługi git.</span><span class="sxs-lookup"><span data-stu-id="d19bf-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="d19bf-117">Co to jest żądanie ściągnięcia?</span><span class="sxs-lookup"><span data-stu-id="d19bf-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="d19bf-118">Jak wspomniano powyżej, warto zająć kilka chwil od momentu, w którym **jest**wykonywane żądanie ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="d19bf-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="d19bf-119">Podczas pracy z usługą git wszelkie zmiany są reprezentowane jako _zatwierdzenia_ , które opisują, w jaki sposób te zmiany są powiązane ze stanem repozytorium, przed wprowadzeniem tych zmian.</span><span class="sxs-lookup"><span data-stu-id="d19bf-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="d19bf-120">Często będą rysowane diagramy, w których zatwierdzenia są rysowane jako okręgi ze strzałkami z poprzednich zatwierdzeń.</span><span class="sxs-lookup"><span data-stu-id="d19bf-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="d19bf-121">Załóżmy, że rozpoczęto udział w _gałęzi_ o nazwie `feature`.</span><span class="sxs-lookup"><span data-stu-id="d19bf-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="d19bf-122">Następnie rozwidlenie **firmy Microsoft/Quantum** może wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="d19bf-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="d19bf-123">Jeśli wprowadzisz zmiany w lokalnym repozytorium, możesz _ściągnąć_ zmiany z innego repozytorium, aby przechwycić wszystkie zmiany, które wystąpiły.</span><span class="sxs-lookup"><span data-stu-id="d19bf-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="d19bf-124">Żądania ściągnięcia działają w ten sam sposób, ale w odwrocie: po otwarciu żądania ściągnięcia zostanie poproszony o repozytorium nadrzędne, aby ściągnąć swój udział w programie.</span><span class="sxs-lookup"><span data-stu-id="d19bf-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="d19bf-125">Gdy otworzysz żądanie ściągnięcia do jednego z naszych repozytoriów, w serwisie GitHub zostanie wyświetlona szansa dla innych osób w społeczności, aby zobaczyć podsumowanie Twoich zmian oraz dodać do nich komentarze i sugestie dotyczące tego, jak pomóc Ci jeszcze lepszym udostępnieniu.</span><span class="sxs-lookup"><span data-stu-id="d19bf-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="d19bf-126">Dzięki temu procesowi firma Microsoft może korzystać z funkcji usługi GitHub w celu ulepszania udziałów i zapewnienia wysokiej jakości produktu dla społeczności programistycznej usługi Quantum.</span><span class="sxs-lookup"><span data-stu-id="d19bf-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="d19bf-127">Jak utworzyć żądanie ściągnięcia</span><span class="sxs-lookup"><span data-stu-id="d19bf-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="d19bf-128">Istnieją dwa podstawowe sposoby tworzenia żądania ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="d19bf-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="d19bf-129">W przypadku małych zmian, które mają wpływ tylko na pojedynczy plik, interfejs sieci Web GitHub może służyć do przepełnienia żądania ściągnięcia w trybie online.</span><span class="sxs-lookup"><span data-stu-id="d19bf-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="d19bf-130">W przypadku bardziej skomplikowanych udziałów często łatwiej jest użyć komputera lokalnego do przygotowania żądania ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="d19bf-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="d19bf-131">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="d19bf-131">Next steps</span></span> ##

<span data-ttu-id="d19bf-132">Gratulujemy korzystania z usługi git, aby pomóc społeczności usługi Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="d19bf-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="d19bf-133">Aby dowiedzieć się więcej o sposobie współtworzenia kodu, przejdź do poniższego przewodnika.</span><span class="sxs-lookup"><span data-stu-id="d19bf-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d19bf-134">Dowiedz się, jak współtworzyć kod</span><span class="sxs-lookup"><span data-stu-id="d19bf-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
