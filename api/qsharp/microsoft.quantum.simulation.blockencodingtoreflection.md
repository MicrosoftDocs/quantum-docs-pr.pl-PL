---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847254"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="379b5-102">BlockEncodingToReflection, funkcja</span><span class="sxs-lookup"><span data-stu-id="379b5-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="379b5-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="379b5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="379b5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="379b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="379b5-105">Konwertuje element na `BlockEncoding` odpowiednik `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="379b5-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="379b5-106">Oznacza to, że w przypadku `BlockEncoding` jednostkowego $U $, który koduje część operatora $H $ Interest, konwertuje ją na `BlockEncodingReflection` $U "$, który koduje ten sam operator, ale również spełnia $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="379b5-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="379b5-107">Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="379b5-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="379b5-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="379b5-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="379b5-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="379b5-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="379b5-110">`BlockEncoding`$U jednostkowe $ do przekonwertowania na odbicie.</span><span class="sxs-lookup"><span data-stu-id="379b5-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="379b5-111">Wynik: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="379b5-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="379b5-112">Jednostkowy $U "$ działa wspólnie w przypadku rejestrów `a` i `s` blokują $H $ i spełniają $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="379b5-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="379b5-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="379b5-113">Remarks</span></span>

<span data-ttu-id="379b5-114">Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="379b5-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="379b5-115">Odwołania</span><span class="sxs-lookup"><span data-stu-id="379b5-115">References</span></span>

- <span data-ttu-id="379b5-116">Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="379b5-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="379b5-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="379b5-117">See Also</span></span>

- [<span data-ttu-id="379b5-118">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="379b5-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="379b5-119">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="379b5-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)