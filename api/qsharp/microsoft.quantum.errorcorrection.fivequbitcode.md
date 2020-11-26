---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200887"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="10dba-102">FiveQubitCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="10dba-102">FiveQubitCode function</span></span>

<span data-ttu-id="10dba-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="10dba-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="10dba-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10dba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10dba-105">Zwraca wartość QECC reprezentującą ⟦ 5, 1, 3 ⟧ kodu kodera i dekodera z pomiarem Syndrome w miejscu.</span><span class="sxs-lookup"><span data-stu-id="10dba-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="10dba-106">Wynik: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="10dba-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="10dba-107">Zwraca implementację kodu korekty błędu Quantum przez określenie `QECC` typu.</span><span class="sxs-lookup"><span data-stu-id="10dba-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="10dba-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="10dba-108">Remarks</span></span>

<span data-ttu-id="10dba-109">Ten kod został znaleziony niezależnie w następujących dwóch dokumentach:</span><span class="sxs-lookup"><span data-stu-id="10dba-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="10dba-110">C.</span><span class="sxs-lookup"><span data-stu-id="10dba-110">C.</span></span> <span data-ttu-id="10dba-111">C.</span><span class="sxs-lookup"><span data-stu-id="10dba-111">H.</span></span> <span data-ttu-id="10dba-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="10dba-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="10dba-113">Smolin i W. K.</span><span class="sxs-lookup"><span data-stu-id="10dba-113">Smolin and W. K.</span></span> <span data-ttu-id="10dba-114">Wootters, "mieszane Stany Entanglement i Korekcja błędów Quantum," fizyczny. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 i</span><span class="sxs-lookup"><span data-stu-id="10dba-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="10dba-115">®.</span><span class="sxs-lookup"><span data-stu-id="10dba-115">R.</span></span> <span data-ttu-id="10dba-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="10dba-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="10dba-117">Paz i W. H.</span><span class="sxs-lookup"><span data-stu-id="10dba-117">Paz and W. H.</span></span> <span data-ttu-id="10dba-118">Zurek, "doskonały kod korekcji błędów Quantum", "fizyczny. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="10dba-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="10dba-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="10dba-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>