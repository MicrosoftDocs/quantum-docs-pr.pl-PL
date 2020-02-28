---
title: Math w bibliotekach standardowych Q
description: 'Dowiedz się więcej o klasycznych funkcjach matematycznych w bibliotekach Q # Standard, które są używane z wbudowanymi typami danych.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906155"
---
# <a name="classical-mathematical-functions"></a>Klasyczne funkcje matematyczne #

Te funkcje są głównie używane do pracy z wbudowanymi typami danych Q # `Int`, `Double`i `Range`.

Operacja <xref:microsoft.quantum.intrinsic.random> ma `(Double[] => Int)`sygnatury.
Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int`.
Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie. n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.
Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.
