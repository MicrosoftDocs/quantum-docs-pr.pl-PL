---
title: 'Biblioteki Q # standardowe — Math | Microsoft Docs'
description: 'Biblioteki Q # standardowe — Math'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184461"
---
# <a name="classical-mathematical-functions"></a>Klasyczne funkcje matematyczne #

Te funkcje są głównie używane do pracy z wbudowanymi typami danych Q # `Int`, `Double`i `Range`.

Operacja <xref:microsoft.quantum.intrinsic.random> ma `(Double[] => Int)`sygnatury.
Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int`.
Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie. n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.
Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.