---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712343"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="abeb0-102">FiveQubitCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="abeb0-102">FiveQubitCode function</span></span>

<span data-ttu-id="abeb0-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="abeb0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="abeb0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="abeb0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="abeb0-105">Zwraca wartość QECC reprezentującą ⟦ 5, 1, 3 ⟧ kodu kodera i dekodera z pomiarem Syndrome w miejscu.</span><span class="sxs-lookup"><span data-stu-id="abeb0-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="abeb0-106">Wynik: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="abeb0-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="abeb0-107">Zwraca implementację kodu korekty błędu Quantum przez określenie `QECC` typu.</span><span class="sxs-lookup"><span data-stu-id="abeb0-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="abeb0-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="abeb0-108">Remarks</span></span>

<span data-ttu-id="abeb0-109">Ten kod został znaleziony niezależnie w następujących dwóch dokumentach:</span><span class="sxs-lookup"><span data-stu-id="abeb0-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="abeb0-110">C.</span><span class="sxs-lookup"><span data-stu-id="abeb0-110">C.</span></span> <span data-ttu-id="abeb0-111">C.</span><span class="sxs-lookup"><span data-stu-id="abeb0-111">H.</span></span> <span data-ttu-id="abeb0-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="abeb0-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="abeb0-113">Smolin i W. K.</span><span class="sxs-lookup"><span data-stu-id="abeb0-113">Smolin and W. K.</span></span> <span data-ttu-id="abeb0-114">Wootters, "mieszane Stany Entanglement i Korekcja błędów Quantum," fizyczny. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 i</span><span class="sxs-lookup"><span data-stu-id="abeb0-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="abeb0-115">®.</span><span class="sxs-lookup"><span data-stu-id="abeb0-115">R.</span></span> <span data-ttu-id="abeb0-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="abeb0-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="abeb0-117">Paz i W. H.</span><span class="sxs-lookup"><span data-stu-id="abeb0-117">Paz and W. H.</span></span> <span data-ttu-id="abeb0-118">Zurek, "doskonały kod korekcji błędów Quantum", "fizyczny. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="abeb0-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="abeb0-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="abeb0-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>