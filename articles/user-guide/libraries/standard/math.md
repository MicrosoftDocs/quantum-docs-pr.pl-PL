---
title: Obliczenia matematyczne w Q# bibliotekach standardowych
description: Dowiedz się więcej o klasycznych funkcjach matematycznych w Q# bibliotekach standardowych, które są używane z wbudowanymi typami danych.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853996"
---
# <a name="classical-mathematical-functions"></a>Klasyczne funkcje matematyczne #

Te funkcje są używane głównie do pracy z Q# wbudowanymi typami danych, `Int` `Double` i `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>Operacja ma sygnaturę `(Double[] => Int)` .
Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int` .
Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie. n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.
Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.
