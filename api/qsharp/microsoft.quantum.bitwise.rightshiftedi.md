---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209778"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="bc20b-102">RightShiftedI, funkcja</span><span class="sxs-lookup"><span data-stu-id="bc20b-102">RightShiftedI function</span></span>

<span data-ttu-id="bc20b-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="bc20b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bc20b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc20b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc20b-105">Przenosi bitową reprezentację liczby bezpośrednio przez daną liczbę bitów.</span><span class="sxs-lookup"><span data-stu-id="bc20b-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="bc20b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bc20b-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="bc20b-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc20b-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc20b-108">Liczba, której reprezentacja bitowa ma zostać przesunięta w prawo (mniej znaczące).</span><span class="sxs-lookup"><span data-stu-id="bc20b-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="bc20b-109">kwota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc20b-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc20b-110">Liczba bitów, przez którą ma `value` zostać przesunięta w prawo.</span><span class="sxs-lookup"><span data-stu-id="bc20b-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="bc20b-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc20b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc20b-112">Wartość `value` , przesunięta w prawo przez `amount` bity.</span><span class="sxs-lookup"><span data-stu-id="bc20b-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc20b-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bc20b-113">Remarks</span></span>

<span data-ttu-id="bc20b-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="bc20b-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```