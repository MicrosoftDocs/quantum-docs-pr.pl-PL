---
uid: Microsoft.Quantum.Bitwise.Parity
title: Funkcja parzystości
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842129"
---
# <a name="parity-function"></a><span data-ttu-id="b96cf-102">Funkcja parzystości</span><span class="sxs-lookup"><span data-stu-id="b96cf-102">Parity function</span></span>

<span data-ttu-id="b96cf-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="b96cf-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="b96cf-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b96cf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b96cf-105">Zwraca bitową PARZYSTość liczby całkowitej (1, jeśli jej reprezentacja binarna zawiera nieparzystą liczbę elementów i 0 w przeciwnym razie).</span><span class="sxs-lookup"><span data-stu-id="b96cf-105">Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).</span></span>

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b96cf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b96cf-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b96cf-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b96cf-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="b96cf-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b96cf-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="b96cf-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="b96cf-109">Example</span></span>

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```