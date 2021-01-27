---
title: Otwieranie żądań ściągnięcia
description: Dowiedz się, jak przesłać żądanie ściągnięcia w usłudze GitHub, gdy wszystko jest gotowe do współtworzenia kodu lub dokumentacji do Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: a936283f3e51da9b97b8145bad3ab765b6423458
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858473"
---
# <a name="opening-pull-requests"></a>Otwieranie żądań ściągnięcia #

Cała dokumentacja zestawu Quantum Development Kit jest zarządzana przy użyciu systemu kontroli wersji Git przy użyciu kilku repozytoriów hostowanych w serwisie GitHub.
Korzystanie z usługi git i usługi GitHub ułatwia współpracę w szerokim zakresie w zestawie Quantum Development Kit.
W szczególności każde repozytorium git może zostać sklonowane lub rozwidlenie w celu przetworzenia całkowicie niezależnej kopii tego repozytorium.
Dzięki temu można pracować nad Twoim udziałem przy użyciu narzędzi i w preferowany tempie.

Gdy wszystko będzie gotowe, możesz wysłać nam żądanie dołączenia Twojego wkładu do naszych repozytoriów, korzystając z funkcji _żądania ściągnięcia_ usługi GitHub.
Strona dla każdego żądania ściągnięcia zawiera szczegółowe informacje o wszystkich zmianach, które wprowadzają swój wkład, listę komentarzy dotyczących Twojego wkładu oraz zestaw narzędzi do przeglądu, które mogą być używane przez innych członków społeczności do przekazywania opinii i porad.

> [!NOTE]
> Chociaż pełny samouczek dotyczący usługi git wykracza poza zakres tego przewodnika, można zasugerować następujące linki, aby uzyskać więcej zasobów dotyczących uczenia usługi git:
>
> - [Poznaj usługę git](https://www.atlassian.com/git): zestaw samouczków usługi git Atlassian.
> - [Kontrola wersji w Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Przewodnik po użyciu Visual Studio Code jako graficzny interfejs użytkownika dla usługi git.
> - [Laboratorium uczenia GitHub](https://lab.github.com/): zestaw kursów online do korzystania z usługi git, usługi GitHub i powiązanych technologii.
> - [Wizualizacja git](https://git-school.github.io/visualizing-git/): interaktywne narzędzie do wizualizacji sposobu zmiany stanu repozytorium przez polecenia usługi git.
> - [Kontrola wersji za pomocą narzędzia Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): samouczek usługi git ukierunkowany na obliczenia naukowe.
> - [Informacje o rozgałęzieniu usługi git](https://learngitbranching.js.org/): interaktywny zestaw rozgałęzień i układanki w celu uzyskania pomocy dotyczącej nowych funkcji usługi git.

## <a name="what-is-a-pull-request"></a>Co to jest żądanie ściągnięcia? ##

Jak wspomniano powyżej, warto zająć kilka chwil od momentu, w którym **jest** wykonywane żądanie ściągnięcia.
Podczas pracy z usługą git wszelkie zmiany są reprezentowane jako _zatwierdzenia_ , które opisują, w jaki sposób te zmiany są powiązane ze stanem repozytorium, przed wprowadzeniem tych zmian.
Często będą rysowane diagramy, w których zatwierdzenia są rysowane jako okręgi ze strzałkami z poprzednich zatwierdzeń.

Załóżmy, że rozpoczęto udział w _gałęzi_ o nazwie `feature` .
Następnie rozwidlenie **firmy Microsoft/Quantum** może wyglądać następująco:

![Gałąź robocza w usłudze GitHub](~/media/git-workflow-step0.png)

Jeśli wprowadzisz zmiany w lokalnym repozytorium, możesz _ściągnąć_ zmiany z innego repozytorium, aby przechwycić wszystkie zmiany, które wystąpiły.

![Ściąganie i scalanie zmian z repozytorium nadrzędnego](~/media/git-workflow-step1.png)

Żądania ściągnięcia działają w ten sam sposób, ale w odwrocie: po otwarciu żądania ściągnięcia zostanie poproszony o repozytorium nadrzędne, aby ściągnąć swój udział w programie.

![Żądanie ściągnięcia zmian z powrotem do oryginalnego repozytorium](~/media/git-workflow-step2.png)

Gdy otworzysz żądanie ściągnięcia do jednego z naszych repozytoriów, w serwisie GitHub zostanie wyświetlona szansa dla innych osób w społeczności, aby zobaczyć podsumowanie Twoich zmian oraz dodać do nich komentarze i sugestie dotyczące tego, jak pomóc Ci jeszcze lepszym udostępnieniu.

![Zrzut ekranu żądania ściągnięcia w usłudze GitHub](~/media/pull-request-header.png)

Dzięki temu procesowi firma Microsoft może korzystać z funkcji usługi GitHub w celu ulepszania udziałów i zapewnienia wysokiej jakości produktu dla społeczności programistycznej usługi Quantum.

## <a name="how-to-make-a-pull-request"></a>Jak utworzyć żądanie ściągnięcia ##

Istnieją dwa podstawowe sposoby tworzenia żądania ściągnięcia.  
W przypadku małych zmian, które mają wpływ tylko na pojedynczy plik, interfejs sieci Web GitHub może służyć do przepełnienia żądania ściągnięcia w trybie online. Po prostu przejdź do pliku, który chcesz edytować, i użyj ikony edycji.  
W przypadku bardziej skomplikowanych udziałów często łatwiej jest sklonować repozytorium na komputerze lokalnym, aby najpierw przygotować żądanie ściągnięcia.

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

## <a name="next-steps"></a>Następne kroki ##

Gratulujemy korzystania z usługi git, aby pomóc społeczności usługi Quantum Development Kit.
Aby dowiedzieć się więcej o sposobie współtworzenia kodu, przejdź do poniższego przewodnika.

> [!div class="nextstepaction"]
> [Dowiedz się, jak współtworzyć kod](xref:microsoft.quantum.contributing.code)
