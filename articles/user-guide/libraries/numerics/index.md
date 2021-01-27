---
title: Wprowadzenie do biblioteki dla liczb kwantowych | Microsoft Docs
description: Wprowadzenie do biblioteki dla liczb kwantowych
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 017fd075596e7b5fb7107d3bc5f149b77dc4e504
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854004"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Wprowadzenie do biblioteki dla liczb kwantowych

Wiele algorytmów kwantowych wykorzystuje [wyrocznie](xref:microsoft.quantum.concepts.oracles), które określają funkcje matematyczne na podstawie superpozycji danych wejściowych.
Na przykład główny składnik algorytmu Shora określa wartość $f(x) = a^x\operatorname{mod} N$ dla stałej wartości $a$, liczbę do uwzględnienia jako współczynnik $N$ oraz $x$, $2n$-kubitową liczbę całkowitą w jednolitej superpozycji we wszystkich ciągach $2n$-bitowych.

Aby uruchomić algorytm Shora na prawdziwym komputerze kwantowym, ta funkcja musi być zapisana odpowiednio do natywnych operacji maszyny docelowej.
Korzystając z binarnej reprezentacji $x$, gdzie $x_i$ oznacza $i$-ty bit, licząc od najmniej istotnego bitu, można zapisać $f(x)$ jako $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.
To wyrażenie można zapisać jako iloczyn (mod N) wyrażeń $a^{2^i x_i}=(a^{2^i})^{x_i}$. Można więc wdrożyć funkcję $f(x)$, korzystając z sekwencji mnożenia (modułowego) $2n$ przez $a^{2^i}$, pod warunkiem, że $x_i$ ma wartość inną niż zero. Stałe $a^{2^i}$ można wstępnie obliczyć i zredukować modulo N przed uruchomieniem algorytmu.

Tę sekwencję kontrolowanego mnożenia modułowego można jeszcze bardziej uprościć: Każde mnożenie można wykonać przy użyciu sekwencji kontrolowanego dodawania modułowego $n$, a każde dodawanie modułowe można utworzyć na podstawie zwykłego dodawania i komparatora.


Biorąc pod uwagę fakt, że osiągnięcie właściwego wdrożenia wymaga wykonania aż tylu kroków, dobrze byłoby mieć dostęp do tej funkcji od samego początku.
To dlatego zestaw Quantum Development Kit zapewnia obsługę dużej liczby funkcji liczbowych.


## <a name="functionality"></a>Funkcjonalność

Oprócz obliczeń arytmetycznych na liczbach całkowitych, które zostały już omówione, biblioteka liczbowa oferuje:

- Funkcjonalność liczb całkowitych ze znakiem/bez znaku (mnożenie, podnoszenie do kwadratu, dzielenie z resztą, inwersja) z danymi wejściowymi w postaci jednej lub dwóch kwantowych liczb całkowitych
- Funkcjonalność liczb stałoprzecinkowych (dodawanie/odejmowanie, mnożenie, podnoszenie do kwadratu, 1/x, obliczanie wartości wielomianu) z danymi wejściowymi w postaci jednej lub dwóch kwantowych liczb stałoprzecinkowych

## <a name="getting-started"></a>Wprowadzenie

> [!div class="nextstepaction"]
> [Dowiedz się więcej o korzystaniu z biblioteki liczbowej](xref:microsoft.quantum.numerics.usage)
