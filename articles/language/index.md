---
title: Język programowania Q#
description: Wprowadzenie do języka Q# w zakresie tworzenia programów kwantowych.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907379"
---
# <a name="the-q-programming-language"></a>Język programowania Q#

## <a name="introduction"></a>Wprowadzenie

Naturalnym modelem obliczeń kwantowych jest traktowanie komputera kwantowego jako koprocesora, podobnego do używanego dla procesorów GPU, FPGA i innych procesorów pomocniczych.
Podstawowa logika sterowania uruchamia klasyczny kod na klasycznym komputerze hosta.
W razie potrzeby program hosta może wywołać podprocedurę, która jest uruchamiana na procesorze pomocniczym.
Po zakończeniu podprocedury program hosta uzyskuje dostęp do wyników podprocedury.

Język Q# (Q-sharp) to język programowania specyficzny dla domeny używany do wyrażania algorytmów kwantowych.
Jest przeznaczony do pisania podprocedur, które są wykonywane na pomocniczym procesorze kwantowym, pod kontrolą klasycznego programu i komputera hosta.
Dopóki procesory kwantowe nie będą szeroko dostępne, procedury języka Q# będą wykonywane w symulatorze.

Język Q# udostępnia niewielki zestaw typów pierwotnych, a także dwa sposoby (tablice i krotki) tworzenia nowych typów strukturalnych.
Obsługuje podstawowy model proceduralny pisania programów, z pętlami i instrukcjami if/then.
Konstrukcje najwyższego poziomu w języku Q# są typami zdefiniowanymi przez użytkownika, operacjami i funkcjami.

W poniższych sekcjach szczegółowo opisano:
- [Model typu](xref:microsoft.quantum.language.type-model)
- [Wyrażenia](xref:microsoft.quantum.language.expressions)
- [Instrukcje](xref:microsoft.quantum.language.statements)
- [Struktura plików](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>Konwencja

Pracujemy nad zapewnieniem spójnego stosowania typowych znaków interpunkcyjnych we wszystkich sytuacjach.
Oczekujemy, że ułatwi to naukę i czytanie języka Q#, ponieważ te znaki zawsze oznaczają to samo, a te same pojęcia są zawsze reprezentowane w ten sam sposób.

Są to:

- Średnik (`;`) służy do zakończenia instrukcji lub jednowierszowej dyrektywy.
  Nie jest używany do żadnego innego celu.
- Przecinek (`,`) służy do oddzielania elementów sekwencji. Jest on używany dla literałów krotek, literałów tablic, list argumentów, definicji krotek i list typów. **Po zmianie z wcześniejszych wersji znak `;` nie jest już obsługiwany jako separator literałów tablicy.**
- Dwukropek (`:`) służy do wprowadzania adnotacji typu. Jest używany głównie w sygnaturach wywołania.
  Ze względu na to, że dwukropek zawsze wprowadza sygnaturę typu, trójstanowy operator warunkowy wprowadzony w wersji 0.3 używa pionowego paska, `|`, aby oddzielić wartości prawdziwe i fałszywe; w tym celu język Q# używa `cond ? tval | fval` zamiast dwukropka jako separatora, jak w języku C.
  
