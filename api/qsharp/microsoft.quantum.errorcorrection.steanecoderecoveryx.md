---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712133"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="1236b-102">SteaneCodeRecoveryX, funkcja</span><span class="sxs-lookup"><span data-stu-id="1236b-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="1236b-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1236b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1236b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1236b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1236b-105">Dekoder dla X części grupy stabilizatorów ⟦ 7, 1, 3 ⟧ Steane w kodzie Quantum.</span><span class="sxs-lookup"><span data-stu-id="1236b-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="1236b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1236b-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="1236b-107">Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="1236b-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="1236b-108">Tablica Syndrome uzyskana z mierzenia częściowej klasy stabilizującej.</span><span class="sxs-lookup"><span data-stu-id="1236b-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="1236b-109">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1236b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1236b-110">Tablica operacji Pauli, która w przypadku zastosowania do zakodowanego systemu Quantum, koryguje błąd odpowiadający `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="1236b-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1236b-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1236b-111">Remarks</span></span>

<span data-ttu-id="1236b-112">Wybrany dekoder używa właściwości CSS kodu ⟦ 7, 1, 3 ⟧ Steane Code, tj. poprawia liczbę błędów X i Z.</span><span class="sxs-lookup"><span data-stu-id="1236b-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="1236b-113">Właściwość kodu jest, że lokalizacja X, odpowiednio, korekta z, ma zostać zastosowana, jest kodowaniem 3-bitowym X, odpowiednio, Z Syndrome, gdy jest traktowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="1236b-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="1236b-114">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="1236b-114">References</span></span>

- <span data-ttu-id="1236b-115">D.</span><span class="sxs-lookup"><span data-stu-id="1236b-115">D.</span></span> <span data-ttu-id="1236b-116">Gottesman, "kody stabilizujące i Korekcja błędów Quantum", "Ph.D., Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="1236b-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="1236b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1236b-117">See Also</span></span>

- [<span data-ttu-id="1236b-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="1236b-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="1236b-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="1236b-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)