---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200479"
---
# <a name="steanecode-function"></a><span data-ttu-id="f9fed-102">SteaneCode, funkcja</span><span class="sxs-lookup"><span data-stu-id="f9fed-102">SteaneCode function</span></span>

<span data-ttu-id="f9fed-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f9fed-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f9fed-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9fed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9fed-105">Zwraca wartość CSS reprezentującą ⟦ 7, 1, 3 ⟧ Steane Code Encoder i dekodera z pomiarem Syndrome w miejscu.</span><span class="sxs-lookup"><span data-stu-id="f9fed-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="f9fed-106">Dane wyjściowe: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="f9fed-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="f9fed-107">Obiekt typu CSS, który gromadzi wszystkie istotne dane w celu kodowania i korekcji błędów dla kodu ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="f9fed-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9fed-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9fed-108">Remarks</span></span>

<span data-ttu-id="f9fed-109">Ten kod został znaleziony w następującym dokumencie:</span><span class="sxs-lookup"><span data-stu-id="f9fed-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="f9fed-110">A.</span><span class="sxs-lookup"><span data-stu-id="f9fed-110">A.</span></span> <span data-ttu-id="f9fed-111">Steane, "wiele zakłóceń cząsteczek i Korekcja błędów Quantum", proc.</span><span class="sxs-lookup"><span data-stu-id="f9fed-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="f9fed-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="f9fed-112">Roy.</span></span> <span data-ttu-id="f9fed-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="f9fed-113">Soc. Lond.</span></span> <span data-ttu-id="f9fed-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="f9fed-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>