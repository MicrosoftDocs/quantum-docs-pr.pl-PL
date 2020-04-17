---
title: Jak nauczyć się wykonywania obliczeń kwantowych w języku Q#?
description: Zasoby dotyczące podstawowej wiedzy matematycznej i fizycznej, które ułatwiają rozpoczęcie pracy z obliczeniami kwantowymi.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 17fc4e7a73f93a86d981996bf8b59309bccb6e67
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907753"
---
# <a name="how-to-learn-about-quantum-computing"></a>Jak dowiedzieć się więcej na temat obliczeń kwantowych?

Zapoznaj się ze wskazówkami dotyczącymi obliczeń kwantowych i pisania swoich pierwszych programów. Nie jest to wyczerpujący przewodnik, ale raczej dobre miejsce, aby zacząć.

## <a name="getting-started-overview"></a>Omówienie rozpoczynania pracy

Artykuł [Wprowadzenie do zestawu Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) zawiera ogólne omówienie obliczeń kwantowych w języku Q#, między innymi samouczki dotyczące pisania pierwszego programu języka Q#, przewodniki wprowadzające, a także wprowadzenie do bibliotek kwantowych języka Q# umożliwiających opracowywanie programów kwantowych.

## <a name="learning-the-basics-what-do-you-need-to-know"></a>Nauka podstawowych informacji: co należy wiedzieć?

Nie musisz znać fizyki kwantowej, aby poznać język Q# i obliczenia kwantowe oraz rozpocząć pisanie aplikacji kwantowych.

Te pojęcia stanowią dobre wprowadzenie do podstawowej wiedzy wymaganej do rozpoczęcia kodowania programów kwantowych.  

* [Podstawowa mechanika kwantowa](xref:microsoft.quantum.concepts.intro): Właśnie powiedzieliśmy, że nie trzeba znać fizyki kwantowej, aby rozpocząć kodowanie (i to prawda!). Jednak niektóre podstawowe pojęcia mechaniki kwantowej i powiązana notacja matematyczna będą pomocne w poznawaniu programowania kwantowego.

* **Algebra liniowa (wektory i macierze)** : w obliczeniach kwantowych stany kwantowe są reprezentowane przez wektory, a operacje kwantowe są liniowymi transformacjami stosowanymi do tych wektorów.  Oto [samouczek w notesie Jupyter dotyczący algebry liniowej](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).  Więcej informacji na temat algebry liniowej można też znaleźć w naszym przewodniku po koncepcjach dotyczącym [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors).

* **Arytmetyka zespolona**: współczynniki wektorów stanu kwantowego to liczby zespolone. Niektóre podstawowe pojęcia obliczeń kwantowych można zrozumieć bez znajomości liczb zespolonych, lecz szybko trzeba będzie włączyć je do używanego zestawu narzędzi kwantowych.  Oto [samouczek w notesie Jupyter dotyczący arytmetyki zespolonej](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic), w którym objaśniono podstawy matematyczne wymagane do pracy z obliczeniami kwantowymi. 

Teraz, gdy znasz już podstawy, możesz zacząć uczyć się pisania programów kwantowych.  Istnieje wiele sposobów dalszej pracy:

## <a name="do-the-quantum-katas"></a>Wykonywanie instrukcji podanych w artykułach Quantum Kata

[Quantum Kata](xref:microsoft.quantum.overview.katas) to seria realizowanych samodzielnie samouczków typu open source, które służą zarówno do nauki elementów obliczeń kwantowych, jak i programowania w języku Q#.  Każdy artykuł Kata odwołuje się do dodatkowych materiałów szkoleniowych, dzięki którym możesz poznać koncepcje obliczeń kwantowych potrzebne do pomyślnego wykonania instrukcji z artykułów Kata.  

## <a name="dive-into-the-theory"></a>Skok w teorię

Być może chcesz bardziej szczegółowo zapoznać się z teorią mechaniki kwantowej i obliczeń kwantowych. Oto lista przydatnych materiałów:

* Zacznij od naszego przewodnika po [pojęciach związanych z obliczeniami kwantowych](xref:microsoft.quantum.concepts.intro) — kompilacji podstawowych koncepcji dotyczących przetwarzania kwantowego.
* Książka _Learn Quantum Computing with Python and Q# (Poznaj obliczenia kwantowe z językami Python i Q#)_ (autorzy: Sarah C. Kaiser i Christophera E. Granade) stanowi doskonałe wprowadzenie dla osób, które mają mało doświadczenia z mechaniką kwantową lub nie mają go wcale, lecz posiadają nieco wiedzy programistycznej.
* Książka _Quantum Computation and Quantum Information (Obliczenia kwantowe i informacja kwantowa)_ (autorzy: Michael A. Nielsen, Isaac L. Chuang) to najczęściej cytowany tekst w dziedzinie obliczeń kwantowych i jest on uważany za standard w tym temacie. Książka zakłada minimalne doświadczenie z zakresu mechaniki kwantowej i informatyki. Jest to doskonały wybór dla czytelników, którzy chcą formalnego wprowadzenia do tematu, a także dla czytelników, którzy szukają szczegółowych informacji o zaawansowanych pojęciach.
* Publikacje MIT OpenCourseWare obejmują doskonały [kurs online](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) polecany przez Allana Adamsa do nauki podstaw mechaniki kwantowej. Idealny dla deweloperów, którzy chcą lepiej zrozumieć fizykę leżącą u podstaw tych zagadnień.

## <a name="join-the-quantum-community"></a>Dołącz do społeczności kwantowej

Nie musisz uczyć się tego samodzielnie — duża społeczność amatorów i ekspertów służy pomocą. Nie obawiaj się pytać!

* Jeśli masz jakiekolwiek pytania dotyczące języka Q# lub obliczeń kwantowych, nie wahaj się i zajrzyj do witryny Quantum Computing StackExchange. Jeśli nie znajdziesz swojego konkretnego pytania, zawsze możesz zadać nowe. 
* Zapoznaj się z [blogiem języka Q#](https://devblogs.microsoft.com/qsharp/) i blogiem [Microsoft Quantum Blog](https://cloudblogs.microsoft.com/quantum/), aby być na bieżąco z nowościami i zasobami dotyczącymi języka Q#.
* Zajrzyj do witryn [Q# Community](https://qsharp.community/) i [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp), aby znaleźć więcej zasobów i materiałów.

 Jeśli szukasz kursu dotyczącego obliczeń kwantowych, [społeczność Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) może pomóc w uzyskaniu programu nauki.  

