---
uid: Microsoft.Quantum.Canon.Angle
title: Funkcja Angle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718488"
---
# <a name="angle-function"></a><span data-ttu-id="a930d-102">Funkcja Angle</span><span class="sxs-lookup"><span data-stu-id="a930d-102">Angle function</span></span>

<span data-ttu-id="a930d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a930d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a930d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a930d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a930d-105">Zwraca wartość 1, jeśli `index` ma nieparzystą liczbę wartości 1 i-1, jeśli `index` ma parzystą liczbę 1.</span><span class="sxs-lookup"><span data-stu-id="a930d-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="a930d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a930d-106">Description</span></span>

<span data-ttu-id="a930d-107">Wartość odpowiada znakowi współczynnika Rademacher-Walsh spektrum n-zmiennej i funkcji dla danego przypisania, które decyduje o kącie obrotu.</span><span class="sxs-lookup"><span data-stu-id="a930d-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="a930d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a930d-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="a930d-109">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a930d-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a930d-110">Przypisanie wejściowe jako liczba całkowita (od 0 do 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="a930d-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="a930d-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a930d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

