---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842094"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="5a55b-102">RightShiftedL, funkcja</span><span class="sxs-lookup"><span data-stu-id="5a55b-102">RightShiftedL function</span></span>

<span data-ttu-id="5a55b-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="5a55b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="5a55b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a55b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a55b-105">Przenosi bitową reprezentację liczby bezpośrednio przez daną liczbę bitów.</span><span class="sxs-lookup"><span data-stu-id="5a55b-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="5a55b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5a55b-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="5a55b-107">wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5a55b-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5a55b-108">Liczba, której reprezentacja bitowa ma zostać przesunięta w prawo (mniej znaczące).</span><span class="sxs-lookup"><span data-stu-id="5a55b-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="5a55b-109">kwota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a55b-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a55b-110">Liczba bitów, przez którą ma `value` zostać przesunięta w prawo.</span><span class="sxs-lookup"><span data-stu-id="5a55b-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5a55b-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5a55b-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5a55b-112">Wartość `value` , przesunięta w prawo przez `amount` bity.</span><span class="sxs-lookup"><span data-stu-id="5a55b-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a55b-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5a55b-113">Remarks</span></span>

<span data-ttu-id="5a55b-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="5a55b-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```