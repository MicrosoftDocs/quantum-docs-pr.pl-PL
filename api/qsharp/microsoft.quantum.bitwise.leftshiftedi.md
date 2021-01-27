---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845305"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="1d079-102">LeftShiftedI, funkcja</span><span class="sxs-lookup"><span data-stu-id="1d079-102">LeftShiftedI function</span></span>

<span data-ttu-id="1d079-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1d079-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1d079-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d079-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d079-105">Przenosi bitową reprezentację liczby pozostawionej przez daną liczbę bitów.</span><span class="sxs-lookup"><span data-stu-id="1d079-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="1d079-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1d079-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="1d079-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d079-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d079-108">Liczba, której reprezentacja bitowa ma zostać przesunięta w lewo (bardziej znaczące).</span><span class="sxs-lookup"><span data-stu-id="1d079-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="1d079-109">kwota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d079-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d079-110">Liczba bitów, przez którą ma `value` zostać przesunięty w lewo.</span><span class="sxs-lookup"><span data-stu-id="1d079-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="1d079-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d079-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d079-112">Wartość `value` , przesunięta w lewo przez `amount` bity.</span><span class="sxs-lookup"><span data-stu-id="1d079-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d079-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1d079-113">Remarks</span></span>

<span data-ttu-id="1d079-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="1d079-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```