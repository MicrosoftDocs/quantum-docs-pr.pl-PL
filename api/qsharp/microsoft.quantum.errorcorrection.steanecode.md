---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853051"
---
# <a name="steanecode-function"></a><span data-ttu-id="e8179-102">SteaneCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="e8179-102">SteaneCode function</span></span>

<span data-ttu-id="e8179-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e8179-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e8179-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8179-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8179-105">Zwraca wartość CSS reprezentującą ⟦ 7, 1, 3 ⟧ Steane Code Encoder i dekodera z pomiarem Syndrome w miejscu.</span><span class="sxs-lookup"><span data-stu-id="e8179-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="e8179-106">Dane wyjściowe: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="e8179-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="e8179-107">Obiekt typu CSS, który gromadzi wszystkie istotne dane w celu kodowania i korekcji błędów dla kodu ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="e8179-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8179-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8179-108">Remarks</span></span>

<span data-ttu-id="e8179-109">Ten kod został znaleziony w następującym dokumencie:</span><span class="sxs-lookup"><span data-stu-id="e8179-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="e8179-110">A.</span><span class="sxs-lookup"><span data-stu-id="e8179-110">A.</span></span> <span data-ttu-id="e8179-111">Steane, "wiele zakłóceń cząsteczek i Korekcja błędów Quantum", proc.</span><span class="sxs-lookup"><span data-stu-id="e8179-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="e8179-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="e8179-112">Roy.</span></span> <span data-ttu-id="e8179-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="e8179-113">Soc. Lond.</span></span> <span data-ttu-id="e8179-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="e8179-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>