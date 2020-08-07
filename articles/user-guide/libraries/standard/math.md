---
title: Obliczenia matematyczne w Q# bibliotekach standardowych
description: Dowiedz się więcej o klasycznych funkcjach matematycznych w Q# bibliotekach standardowych, które są używane z wbudowanymi typami danych.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868427"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="e92de-103">Klasyczne funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="e92de-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="e92de-104">Te funkcje są używane głównie do pracy z Q# wbudowanymi typami danych, `Int` `Double` i `Range` .</span><span class="sxs-lookup"><span data-stu-id="e92de-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="e92de-105"><xref:microsoft.quantum.intrinsic.random>Operacja ma sygnaturę `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="e92de-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="e92de-106">Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="e92de-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="e92de-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="e92de-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="e92de-108">n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="e92de-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="e92de-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e92de-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
