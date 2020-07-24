---
title: Wprowadzenie do biblioteki dla liczb kwantowych | Microsoft Docs
description: Wprowadzenie do biblioteki dla liczb kwantowych
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871352"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="ca7e3-103">Wprowadzenie do biblioteki dla liczb kwantowych</span><span class="sxs-lookup"><span data-stu-id="ca7e3-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="ca7e3-104">Wiele algorytmów kwantowych wykorzystuje [wyrocznie](xref:microsoft.quantum.concepts.oracles), które określają funkcje matematyczne na podstawie superpozycji danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="ca7e3-105">Na przykład główny składnik algorytmu Shora określa wartość $f(x) = a^x\operatorname{mod} N$ dla stałej wartości $a$, liczbę do uwzględnienia jako współczynnik $N$ oraz $x$, $2n$-kubitową liczbę całkowitą w jednolitej superpozycji we wszystkich ciągach $2n$-bitowych.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="ca7e3-106">Aby uruchomić algorytm Shora na prawdziwym komputerze kwantowym, ta funkcja musi być zapisana odpowiednio do natywnych operacji maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="ca7e3-107">Korzystając z binarnej reprezentacji $x$, gdzie $x_i$ oznacza $i$-ty bit, licząc od najmniej istotnego bitu, można zapisać $f(x)$ jako $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="ca7e3-108">To wyrażenie można zapisać jako iloczyn (mod N) wyrażeń $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="ca7e3-109">Można więc wdrożyć funkcję $f(x)$, korzystając z sekwencji mnożenia (modułowego) $2n$ przez $a^{2^i}$, pod warunkiem, że $x_i$ ma wartość inną niż zero.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="ca7e3-110">Stałe $a^{2^i}$ można wstępnie obliczyć i zredukować modulo N przed uruchomieniem algorytmu.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="ca7e3-111">Tę sekwencję kontrolowanego mnożenia modułowego można jeszcze bardziej uprościć: Każde mnożenie można wykonać przy użyciu sekwencji kontrolowanego dodawania modułowego $n$, a każde dodawanie modułowe można utworzyć na podstawie zwykłego dodawania i komparatora.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="ca7e3-112">Biorąc pod uwagę fakt, że osiągnięcie właściwego wdrożenia wymaga wykonania aż tylu kroków, dobrze byłoby mieć dostęp do tej funkcji od samego początku.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="ca7e3-113">To dlatego zestaw Quantum Development Kit zapewnia obsługę dużej liczby funkcji liczbowych.</span><span class="sxs-lookup"><span data-stu-id="ca7e3-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="ca7e3-114">Funkcjonalność</span><span class="sxs-lookup"><span data-stu-id="ca7e3-114">Functionality</span></span>

<span data-ttu-id="ca7e3-115">Oprócz obliczeń arytmetycznych na liczbach całkowitych, które zostały już omówione, biblioteka liczbowa oferuje:</span><span class="sxs-lookup"><span data-stu-id="ca7e3-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

- <span data-ttu-id="ca7e3-116">Funkcjonalność liczb całkowitych ze znakiem/bez znaku (mnożenie, podnoszenie do kwadratu, dzielenie z resztą, inwersja) z danymi wejściowymi w postaci jednej lub dwóch kwantowych liczb całkowitych</span><span class="sxs-lookup"><span data-stu-id="ca7e3-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
- <span data-ttu-id="ca7e3-117">Funkcjonalność liczb stałoprzecinkowych (dodawanie/odejmowanie, mnożenie, podnoszenie do kwadratu, 1/x, obliczanie wartości wielomianu) z danymi wejściowymi w postaci jednej lub dwóch kwantowych liczb stałoprzecinkowych</span><span class="sxs-lookup"><span data-stu-id="ca7e3-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="ca7e3-118">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="ca7e3-118">Getting started</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ca7e3-119">Dowiedz się więcej o korzystaniu z biblioteki liczbowej</span><span class="sxs-lookup"><span data-stu-id="ca7e3-119">Learn about using the numerics library</span></span>](xref:microsoft.quantum.numerics.usage)
