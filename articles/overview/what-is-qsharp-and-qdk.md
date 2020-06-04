---
title: Co to jest język programowania Q# i zestaw QDK?
description: Dowiedz się więcej o zestawie Microsoft Quantum Development Kit, języku programowania Q# i sposobach tworzenia programów kwantowych.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
ms.openlocfilehash: ede4ad005090e4ac8ffd9b05d27edfa91f8c50ab
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327712"
---
# <a name="what-are-the-q-programming-language-and-qdk"></a>Co to jest język programowania Q# i zestaw QDK?

Q# to język programowania typu open-source firmy Microsoft używany do tworzenia i uruchamiania algorytmów kwantowych. Wchodzi on w skład zestawu Quantum Development Kit (QDK), który zawiera [biblioteki języka Q#](xref:microsoft.quantum.libraries), [symulatory kwantowe](xref:microsoft.quantum.machines), [rozszerzenia dla innych środowisk programistycznych](xref:microsoft.quantum.install) i [dokumentację interfejsu API](xref:microsoft.quantum.standardlibsintro). Oprócz standardowej biblioteki języka Q# zestaw QDK obejmuje biblioteki chemiczne, uczenia maszynowego i liczbowe.

Jako język programowania, Q# zawiera elementy znane z języków Python, C# i F# i obsługuje podstawowy model proceduralny pisania programów z użyciem pętli, instrukcji „jeżeli/to” i wspólnych typów danych. Wprowadzono w nim również nowe struktury danych i operacje specyficzne dla środowiska kwantowego.

## <a name="what-can-i-do-with-the-qdk"></a>Co można zrobić za pomocą zestawu QDK?

QDK to w pełni funkcjonalny zestaw deweloperski dla języka Q#, którego można używać z popularnymi narzędziami i językami do tworzenia aplikacji kwantowych możliwych do uruchamiania w różnych środowiskach. Programy utworzone w języku Q# można uruchamiać jako aplikację wiersza polecenia, za pomocą notesów Jupyter, lub za pomocą hostującego programu utworzonego w języku Python lub na platformie .NET.

### <a name="develop-in-common-tools-and-environments"></a>Opracowywanie w popularnych narzędziach i środowiskach

Zintegruj proces opracowywania programów kwantowych z programem [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) i [notesami Jupyter](xref:microsoft.quantum.install.jupyter). Skorzystaj z wbudowanych interfejsów API do kojarzenia swoich programów z językami macierzystymi [Python](xref:microsoft.quantum.install.python) i [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Wypróbuj operacje kwantowe i biblioteki specyficzne dla dziedziny

Pisz i testuj algorytmy kwantowe, aby eksplorować superpozycje, splątanie i inne operacje kwantowe. Biblioteki języka Q# umożliwiają wykonywanie złożonych operacji kwantowych bez konieczności projektowania sekwencji operacji niskiego poziomu.

### <a name="run-programs-in-simulators"></a>Uruchamianie programów w symulatorach

Uruchamiaj swoje programy kwantowe w symulatorze kwantowym pełnego stanu, symulatorze Toffoli z ograniczonym zakresem lub testuj kod języka Q# w różnych narzędziach do szacowania zasobów. 

## <a name="where-can-i-learn-more"></a>Gdzie mogę dowiedzieć się więcej?

|||
| ---- | ---- |
| **Nie mam doświadczenia w obliczeniach kwantowych** | Zapoznaj się z podstawowymi pojęciami dotyczącymi fizyki kwantowej i obliczeń kwantowych opisanymi w sekcji [Kluczowe pojęcia](xref:microsoft.quantum.overview.understanding).|
| **Chcę lepiej poznać język Q#** | Eksploruj typy, wyrażenia, zmienne i strukturę programu kwantowego opisane w [podręczniku użytkownika języka Q#](xref:microsoft.quantum.guide).|
| **Chcę zacząć pisać programy kwantowe** | Skonfiguruj środowisko języka Q# i rozpocznij pisanie programów kwantowych w [przewodniku Szybki start](xref:microsoft.quantum.install).|

## <a name="how-does-q-work"></a>Jak działa język Q#?

Program napisany w języku Q# można skompilować do autonomicznej aplikacji wiersza polecenia lub wywoływać za pośrednictwem programu hosta napisanego w języku Python lub na platformie .NET.

Podczas kompilowania i uruchamiania programu tworzone jest wystąpienie symulatora kwantowego, do którego jest następnie przekazywany kod Q#. Symulator używa kodu Q# do tworzenia kubitów (symulacji cząstek kwantowych) i stosuje przekształcenia w celu zmodyfikowania ich stanu. Wyniki operacji kwantowych w symulatorze są następnie zwracane do programu.  

Odizolowanie kodu Q# w symulatorze gwarantuje, że algorytmy są zgodne z prawami fizyki kwantowej i mogą działać poprawnie na komputerach kwantowych.

![przepływ kodu Q#](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Jak mogę korzystać z zestawu QDK?

Wszystko, czego potrzebujesz do pisania i uruchamiania programów utworzonych w języku Q#, w tym kompilator języka Q#, biblioteki języka Q# i symulatory kwantowe, możesz instalować i uruchamiać z komputera lokalnego. Na koniec będziesz w stanie uruchamiać zdalnie programy utworzone w języku Q# na rzeczywistym komputerze kwantowym, a do tego czasu symulatory kwantowe znajdujące się w zestawie QDK zapewniają dokładne i niezawodne wyniki.

- Uruchamianie [programu napisanego w języku Q# z poziomu wiersza polecenia](xref:microsoft.quantum.install.standalone) jest najszybszym sposobem na rozpoczęcie pracy.

- Uruchamiaj autonomiczne [notesy Jupyter z funkcją IQ#](xref:microsoft.quantum.install.jupyter) — rozszerzeniem Jupyter umożliwiającym kompilowanie, symulowanie i wizualizowanie programów napisanych w języku Q#.

- Jeśli znasz język [Python](xref:microsoft.quantum.install.python), na początek możesz go użyć jako hostującej platformy programowania hosta. Język Python jest popularny nie tylko wśród deweloperów, ale również wśród naukowców, badaczy i nauczycieli.

- Jeśli masz już doświadczenie w korzystaniu z języków [C#, F# lub VB.NET](xref:microsoft.quantum.install.cs) i znasz środowisko deweloperskie programu Visual Studio, istnieje tylko kilka rozszerzeń, które należy dodać do programu Visual Studio, aby przygotować go do usługi języka Q#.  

## <a name="summary"></a>Podsumowanie

Q# to język programowania typu „open-source” służący do opracowywania programów kwantowych. Dysponuje on bibliotekami, które umożliwiają tworzenie złożonych operacji kwantowych, i symulatorami kwantowymi do dokładnego uruchamiania i testowania programów. Programy napisane w języku Q# mogą działać jako aplikacje autonomiczne lub można je wywoływać z poziomu programu napisanego w języku Python bądź programu hostującego bazującego na platformie .NET. Można je pisać, uruchamiać i testować na komputerze lokalnym.

## <a name="next-steps"></a>Następne kroki

[Algebra liniowa na potrzeby obliczeń kwantowych](xref:microsoft.quantum.overview.algebra)
