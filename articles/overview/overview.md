---
title: Wprowadzenie do obliczeń kwantowych
description: Dowiedz się, czym są obliczenia kwantowe, jakie są możliwości komputerów kwantowych oraz jak możesz nauczyć się obliczeń kwantowych.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866982"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Wprowadzenie do obliczeń kwantowych i zestaw Quantum Development Kit

Microsoft Quantum Development Kit (QDK) to zestaw narzędzi typu open source zaprojektowanych w celu ułatwienia deweloperom uczenia się algorytmów kwantowych i pisania programów kwantowych. Obliczenia kwantowe dają nadzieję na rozwiązanie niektórych największych wyzwań dla naszej planety — tych związanych ze środowiskiem, rolnictwem, medycyną, energetyką, klimatem i materiałoznawstwem, oraz tych, które dopiero się pojawią.  

W przypadku niektórych z tych problemów nawet najbardziej zaawansowane komputery napotykają problemy. Chociaż technologia kwantowa dopiero zaczyna wpływać na środowisko obliczeniowe, może to być proces długoterminowy, który zmieni sposób, w jaki będziemy myśleć o obliczeniach.

## <a name="what-is-quantum-computing"></a>Co to są obliczenia kwantowe?

W nowoczesnym zastosowaniu słowo kwant oznacza najmniejszą możliwą jednostkę dyskretną właściwości fizycznej, zazwyczaj odwołującą się do właściwości cząstek atomowych lub mniejszych. Komputery kwantowe używają rzeczywistych cząstek kwantowych, sztucznych atomów lub grupowych właściwości cząstek kwantowych jako jednostek przetwarzania oraz są duże, złożone i kosztowne.

Korzystając z unikatowych zachowań fizyki kwantowej i stosując je do przetwarzania, komputery kwantowe wprowadzają nowe pojęcia do tradycyjnych metod programowania przy użyciu zachowań fizyki kwantowej, takich jak superpozycja, splątanie i oddziaływania kwantowe.

## <a name="what-can-a-quantum-computer-do"></a>Co może robić komputer kwantowy?

Komputer kwantowy nie jest superkomputerem, który może wykonywać wszystko szybciej, ale istnieje kilka obszarów, w których komputery kwantowe działają wyjątkowo dobrze.

- [Symulacja kwantowa](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Kryptografia](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Wyszukiwanie](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optymalizacja](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Uczenie maszynowe](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Symulacja kwantowa

Ponieważ komputery kwantowe używają zjawisk kwantowych w obliczeniach, dobrze sprawdzają się w modelowaniu innych systemów kwantowych. Fotosynteza, nadprzewodniki i molekuły złożone to przykłady mechanizmów kwantowych, które programy kwantowe mogą symulować.

## <a name="cryptography-and-shors-algorithm"></a>Algorytm kryptograficzny i algorytm Shora

W 1994 r. Peter Shor wykazał, że skalowalny komputer kwantowy może złamać powszechnie używane techniki szyfrowania, takie jak algorytm RSA. Kryptografia klasyczna bazuje na niewykonalności problemów, takich jak faktoryzacja liczb całkowitych lub logarytmy dyskretne, z których wiele można rozwiązać wydajniej przy użyciu komputerów kwantowych.

## <a name="search-and-grovers-algorithm"></a>Wyszukiwanie i algorytm Grovera

W 1996 r. Lov Grover opracował algorytm kwantowy, który znacząco przyspieszył rozwiązanie dla wyszukiwania danych bez struktury, uruchamiając wyszukiwanie w mniejszej liczbie kroków niż klasyczny algorytm.

## <a name="quantum-inspired-computing-and-optimization"></a>Przetwarzanie i optymalizacja inspirowane metodami kwantowymi

Algorytmy inspirowane metodami kwantowymi korzystają z zasad kwantowych do zwiększenia szybkości i dokładności, ale są implementowane w klasycznych systemach komputerowych. Dzięki temu deweloperzy mogą korzystać z nowych technik kwantowych dzisiaj bez oczekiwania na sprzęt kwantowy, który nadal jest na wczesnym etapie rozwoju.

Optymalizacja to proces znajdowania najlepszego rozwiązania problemu, uwzględniając jego żądany wynik i ograniczenia. Takie czynniki jak koszt, jakość lub czas produkcyjny odgrywają role w krytycznych decyzjach podejmowanych w branży i nauce. Algorytmy optymalizacji inspirowane metodami kwantowymi działające na współczesnych komputerach klasycznych mogą znajdować rozwiązania, które do tej pory nie były możliwe. Oprócz optymalizacji ruchu w celu ograniczenia zanieczyszczeń istnieją takie problemy jak przypisywanie bramek na lotniskach, dostarczanie paczek i planowanie zadań. Dzięki przełomom w materiałoznawstwie zostaną wprowadzone nowe formy energii, baterie o większej pojemności oraz lżejsze i trwalsze materiały.

> [!NOTE]
> Dowiedz się więcej na temat sposobu korzystania z obliczeń inspirowanych rozwiązaniami kwantowymi firmy Microsoft w zakresie [materiałoznawstwa](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [zarządzania ryzykiem](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) i [medycyny](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Kwantowe uczenie maszynowe

Uczenie maszynowe na komputerach klasycznych rewolucjonizuje świat nauki i biznesu. Jednak wysoki koszt obliczeń trenowania modeli utrudnia rozwój i zakres pola. Obszar kwantowego uczenia maszynowego obejmuje opracowywanie i implementowanie oprogramowania kwantowego, które umożliwia uczenie maszynowe działające szybciej niż komputery klasyczne.

Zestaw Quantum Development Kit jest dostępny z [biblioteką Quantum Machine Learning](xref:microsoft.quantum.machine-learning.concepts.intro), która umożliwia uruchamianie hybrydowych, kwantowo-klasycznych eksperymentów uczenia maszynowego. Biblioteka zawiera przykłady i samouczki, a także udostępnia narzędzia niezbędne do zaimplementowania nowego hybrydowego algorytmu kwantowo-klasycznego, skoncentrowanego na obwodzie klasyfikatora kwantowego w celu rozwiązywania nadzorowanych problemów klasyfikacji.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Język Q# i zestaw Microsoft Quantum Development Kit (QDK)

Q# to język programowania typu open-source firmy Microsoft używany do tworzenia i uruchamiania algorytmów kwantowych. Jest on częścią zestawu [QDK](https://docs.microsoft.com/quantum/), w pełni funkcjonalnego zestawu deweloperskiego dla języka Q#, którego można używać ze standardowymi narzędziami i językami do tworzenia aplikacji kwantowych. Można je uruchamiać w różnych środowiskach, w tym wbudowanym kwantowym symulatorze pełnego stanu.

Istnieją rozszerzenia dla programów Visual Studio i VS Code oraz pakiety do użycia z językiem Python i aplikacją Jupyter Notebook.

Zestaw QDK zawiera standardową bibliotekę oraz specjalistyczne biblioteki z zakresu chemii, uczenia maszynowego i liczb.

Dokumentacja zawiera przewodnik po języku Q#, samouczki i przykładowy kod umożliwiający szybkie rozpoczęcie pracy oraz rozbudowane artykuły ułatwiające szczegółowe poznanie pojęć związanych z obliczeniami kwantowymi.  

## <a name="microsoft-quantum-hardware-partners"></a>Partnerzy sprzętu kwantowego firmy Microsoft

Firma Microsoft współpracuje z producentami sprzętu kwantowego, aby zapewnić deweloperom dostęp w chmurze do sprzętu kwantowego. Korzystając z platformy [Azure Quantum](https://azure.microsoft.com/services/quantum/) i języka Q#, deweloperzy będą mogli eksplorować algorytmy kwantowe i uruchamiać swoje programy kwantowe na różnych typach sprzętu kwantowego.

Rozwiązania [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) i [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) używają procesorów **opartych na uwięzionych jonach**, używając w tym celu jonów uwięzionych w polu elektronicznym, a rozwiązanie [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) używa obwodów nadprzewodnictwa.

## <a name="next-steps"></a>Następne kroki

[Kluczowe pojęcia dotyczące przetwarzania kwantowego](xref:microsoft.quantum.overview.understanding)
[Przewodniki Szybki start](xref:microsoft.quantum.welcome)