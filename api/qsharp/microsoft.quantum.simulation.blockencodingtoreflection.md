---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225350"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="18ee8-102">BlockEncodingToReflection, funkcja</span><span class="sxs-lookup"><span data-stu-id="18ee8-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="18ee8-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="18ee8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="18ee8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18ee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18ee8-105">Konwertuje element na `BlockEncoding` odpowiednik `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="18ee8-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="18ee8-106">Oznacza to, że w przypadku `BlockEncoding` jednostkowego $U $, który koduje część operatora $H $ Interest, konwertuje ją na `BlockEncodingReflection` $U "$, który koduje ten sam operator, ale również spełnia $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="18ee8-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="18ee8-107">Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="18ee8-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="18ee8-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="18ee8-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="18ee8-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="18ee8-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="18ee8-110">`BlockEncoding`$U jednostkowe $ do przekonwertowania na odbicie.</span><span class="sxs-lookup"><span data-stu-id="18ee8-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="18ee8-111">Wynik: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="18ee8-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="18ee8-112">Jednostkowy $U "$ działa wspólnie w przypadku rejestrów `a` i `s` blokują $H $ i spełniają $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="18ee8-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="18ee8-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="18ee8-113">Remarks</span></span>

<span data-ttu-id="18ee8-114">Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="18ee8-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="18ee8-115">Odwołania</span><span class="sxs-lookup"><span data-stu-id="18ee8-115">References</span></span>

- <span data-ttu-id="18ee8-116">Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="18ee8-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="18ee8-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18ee8-117">See Also</span></span>

- [<span data-ttu-id="18ee8-118">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="18ee8-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="18ee8-119">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="18ee8-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)