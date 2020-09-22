---
title: Biblioteki zestawu Quantum Development Kit
description: Omówienie biblioteki standardowej, chemicznej i numerycznej zawartych w zestawie Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835727"
---
# <a name="overview-of-no-locq-libraries"></a>Omówienie bibliotek języka Q#
Zestaw Quantum Development Kit jest dostarczany z kilkoma bibliotekami, które ułatwiają tworzenie aplikacji kwantowych w języku Q#.
W tej sekcji dokumentacji opisano te biblioteki i sposoby ich używania w programach.

- [**Biblioteki standardowe**](xref:microsoft.quantum.libraries.standard.intro): W tej sekcji opisano preludium, bibliotekę definiującą interfejs między programami Q# i maszynami docelowymi, oraz kanon, bibliotekę języka Q# udostępniającą operacje i funkcje ogólnego zastosowania przydatne podczas pisania programów w języku Q#.
- [**Biblioteka dla chemii kwantowej**](xref:microsoft.quantum.chemistry.concepts.intro): W tej sekcji opisano bibliotekę dla chemii kwantowej udostępniającą model danych na potrzeby ładowania reprezentacji funkcji Hamiltona dla fermionów, a także operacje i funkcje symulacji kwantowej, które działają w tych reprezentacjach.
- [**Biblioteka dla liczb kwantowych**](xref:microsoft.quantum.numerics.intro): W tej sekcji opisano bibliotekę dla liczb kwantowych, która udostępnia implementacje dla hosta funkcji matematycznych. Obsługuje ona reprezentacje liczb całkowitych (ze znakiem i bez znaki) oraz liczb stałoprzecinkowych.
- [**Biblioteka dla kwantowego uczenia maszynowego**](xref:microsoft.quantum.machine-learning.concepts.intro): Ta sekcja zawiera opis biblioteki dla kwantowego uczenia maszynowego udostępniającej implementację klasyfikatorów sekwencyjnych, które korzystają z obliczeń kwantowych w celu rozumienia danych.

Kod źródłowy tych bibliotek oraz przykłady kodu można uzyskać z witryny GitHub.
Aby uzyskać więcej informacji, zobacz [Licencjonowanie](xref:microsoft.quantum.libraries.licensing). Należy zauważyć, że odwołania do pakietów („pliki binarne”) są dostępne również dla bibliotek, które oferują inny sposób dołączania bibliotek do projektów.
Można je łatwo uzyskać z witryny [NuGet](https://nuget.org).
