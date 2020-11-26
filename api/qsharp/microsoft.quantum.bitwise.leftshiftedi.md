---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209863"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="f64bc-102">LeftShiftedI, funkcja</span><span class="sxs-lookup"><span data-stu-id="f64bc-102">LeftShiftedI function</span></span>

<span data-ttu-id="f64bc-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f64bc-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f64bc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f64bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f64bc-105">Przenosi bitową reprezentację liczby pozostawionej przez daną liczbę bitów.</span><span class="sxs-lookup"><span data-stu-id="f64bc-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f64bc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f64bc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f64bc-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f64bc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f64bc-108">Liczba, której reprezentacja bitowa ma zostać przesunięta w lewo (bardziej znaczące).</span><span class="sxs-lookup"><span data-stu-id="f64bc-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="f64bc-109">kwota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f64bc-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f64bc-110">Liczba bitów, przez którą ma `value` zostać przesunięty w lewo.</span><span class="sxs-lookup"><span data-stu-id="f64bc-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="f64bc-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f64bc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f64bc-112">Wartość `value` , przesunięta w lewo przez `amount` bity.</span><span class="sxs-lookup"><span data-stu-id="f64bc-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="f64bc-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f64bc-113">Remarks</span></span>

<span data-ttu-id="f64bc-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="f64bc-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```