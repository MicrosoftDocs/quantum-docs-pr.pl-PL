---
title: Math w bibliotekach standardowych Q
description: 'Dowiedz się więcej o klasycznych funkcjach matematycznych w bibliotekach Q # Standard, które są używane z wbudowanymi typami danych.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275658"
---
# <a name="classical-mathematical-functions"></a>Klasyczne funkcje matematyczne #

Te funkcje są głównie używane do pracy z wbudowanymi typami danych Q # `Int` , `Double` i `Range` .

<xref:microsoft.quantum.intrinsic.random>Operacja ma sygnaturę `(Double[] => Int)` .
Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int` .
Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie. n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.
Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.
