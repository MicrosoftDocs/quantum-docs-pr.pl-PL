---
title: Obliczenia matematyczne w Q# bibliotekach standardowych
description: Dowiedz się więcej o klasycznych funkcjach matematycznych w Q# bibliotekach standardowych, które są używane z wbudowanymi typami danych.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692051"
---
# <a name="classical-mathematical-functions"></a>Klasyczne funkcje matematyczne #

Te funkcje są używane głównie do pracy z Q# wbudowanymi typami danych, `Int` `Double` i `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>Operacja ma sygnaturę `(Double[] => Int)` .
Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int` .
Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie. n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.
Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.
