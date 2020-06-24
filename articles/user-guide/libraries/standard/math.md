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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="d11eb-103">Klasyczne funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="d11eb-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="d11eb-104">Te funkcje są głównie używane do pracy z wbudowanymi typami danych Q # `Int` , `Double` i `Range` .</span><span class="sxs-lookup"><span data-stu-id="d11eb-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="d11eb-105"><xref:microsoft.quantum.intrinsic.random>Operacja ma sygnaturę `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="d11eb-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="d11eb-106">Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="d11eb-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="d11eb-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="d11eb-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="d11eb-108">n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="d11eb-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="d11eb-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="d11eb-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
