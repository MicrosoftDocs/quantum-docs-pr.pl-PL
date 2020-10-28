---
uid: Microsoft.Quantum.Canon.QFT
title: QFT, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715652"
---
# <a name="qft-operation"></a><span data-ttu-id="0b6fe-102">QFT, operacja</span><span class="sxs-lookup"><span data-stu-id="0b6fe-102">QFT operation</span></span>

<span data-ttu-id="0b6fe-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b6fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b6fe-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b6fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b6fe-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji big-endian.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="0b6fe-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0b6fe-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="0b6fe-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0b6fe-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0b6fe-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="0b6fe-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b6fe-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b6fe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0b6fe-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0b6fe-110">Remarks</span></span>

<span data-ttu-id="0b6fe-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu big endian.</span><span class="sxs-lookup"><span data-stu-id="0b6fe-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b6fe-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0b6fe-112">See Also</span></span>

- [<span data-ttu-id="0b6fe-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="0b6fe-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)