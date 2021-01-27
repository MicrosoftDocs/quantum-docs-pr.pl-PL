---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853141"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="b5744-102">FiveQubitCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="b5744-102">FiveQubitCode function</span></span>

<span data-ttu-id="b5744-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b5744-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b5744-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5744-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5744-105">Zwraca wartość QECC reprezentującą ⟦ 5, 1, 3 ⟧ kodu kodera i dekodera z pomiarem Syndrome w miejscu.</span><span class="sxs-lookup"><span data-stu-id="b5744-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="b5744-106">Wynik: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="b5744-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="b5744-107">Zwraca implementację kodu korekty błędu Quantum przez określenie `QECC` typu.</span><span class="sxs-lookup"><span data-stu-id="b5744-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5744-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b5744-108">Remarks</span></span>

<span data-ttu-id="b5744-109">Ten kod został znaleziony niezależnie w następujących dwóch dokumentach:</span><span class="sxs-lookup"><span data-stu-id="b5744-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="b5744-110">C.</span><span class="sxs-lookup"><span data-stu-id="b5744-110">C.</span></span> <span data-ttu-id="b5744-111">C.</span><span class="sxs-lookup"><span data-stu-id="b5744-111">H.</span></span> <span data-ttu-id="b5744-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="b5744-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="b5744-113">Smolin i W. K.</span><span class="sxs-lookup"><span data-stu-id="b5744-113">Smolin and W. K.</span></span> <span data-ttu-id="b5744-114">Wootters, "mieszane Stany Entanglement i Korekcja błędów Quantum," fizyczny. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 i</span><span class="sxs-lookup"><span data-stu-id="b5744-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="b5744-115">®.</span><span class="sxs-lookup"><span data-stu-id="b5744-115">R.</span></span> <span data-ttu-id="b5744-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="b5744-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="b5744-117">Paz i W. H.</span><span class="sxs-lookup"><span data-stu-id="b5744-117">Paz and W. H.</span></span> <span data-ttu-id="b5744-118">Zurek, "doskonały kod korekcji błędów Quantum", "fizyczny. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="b5744-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="b5744-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="b5744-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>