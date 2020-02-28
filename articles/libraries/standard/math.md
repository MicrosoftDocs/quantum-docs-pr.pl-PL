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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="debb3-103">Klasyczne funkcje matematyczne</span><span class="sxs-lookup"><span data-stu-id="debb3-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="debb3-104">Te funkcje są głównie używane do pracy z wbudowanymi typami danych Q # `Int`, `Double`i `Range`.</span><span class="sxs-lookup"><span data-stu-id="debb3-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="debb3-105">Operacja <xref:microsoft.quantum.intrinsic.random> ma `(Double[] => Int)`sygnatury.</span><span class="sxs-lookup"><span data-stu-id="debb3-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="debb3-106">Pobiera on tablicę podwajania jako dane wejściowe i zwraca losowo wybrany indeks do tablicy jako `Int`.</span><span class="sxs-lookup"><span data-stu-id="debb3-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="debb3-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="debb3-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="debb3-108">n elementy tablicy, które są równe zero są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="debb3-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="debb3-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="debb3-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
