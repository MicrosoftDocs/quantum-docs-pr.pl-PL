---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712418"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="da6f6-102">DecodeFromSteaneCode, operacja</span><span class="sxs-lookup"><span data-stu-id="da6f6-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="da6f6-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="da6f6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="da6f6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da6f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da6f6-105">Operacja kodowania odwrotnego, która mapuje niezakodowany rejestr Quantum na zakodowany rejestr Quantum w ⟦ 7, 1, 3 ⟧ Steane Quantum.</span><span class="sxs-lookup"><span data-stu-id="da6f6-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="da6f6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="da6f6-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="da6f6-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="da6f6-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="da6f6-108">Tablica qubits reprezentująca zakodowany stan logiczny w kodzie 5 qubit.</span><span class="sxs-lookup"><span data-stu-id="da6f6-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="da6f6-109">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="da6f6-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="da6f6-110">Tablica qubit o długości 1 reprezentująca niezakodowany stan w pierwszym parametrze wraz z pomocniczym qubits w drugim parametrze.</span><span class="sxs-lookup"><span data-stu-id="da6f6-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="da6f6-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="da6f6-111">Remarks</span></span>

<span data-ttu-id="da6f6-112">Wybrany dekoder używa właściwości CSS kodu ⟦ 7, 1, 3 ⟧ Steane Code, tj. poprawia liczbę błędów X i Z.</span><span class="sxs-lookup"><span data-stu-id="da6f6-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="da6f6-113">Właściwość kodu jest, że lokalizacja X, odpowiednio, korekta z, ma zostać zastosowana, jest kodowaniem 3-bitowym X, odpowiednio, Z Syndrome, gdy jest traktowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="da6f6-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="da6f6-114">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="da6f6-114">References</span></span>

- <span data-ttu-id="da6f6-115">D.</span><span class="sxs-lookup"><span data-stu-id="da6f6-115">D.</span></span> <span data-ttu-id="da6f6-116">Gottesman, "kody stabilizujące i Korekcja błędów Quantum", "Ph.D., Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="da6f6-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="da6f6-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="da6f6-117">See Also</span></span>

- [<span data-ttu-id="da6f6-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="da6f6-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="da6f6-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="da6f6-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="da6f6-120">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="da6f6-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)