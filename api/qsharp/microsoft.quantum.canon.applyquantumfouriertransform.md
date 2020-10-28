---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717794"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="9dd02-102">ApplyQuantumFourierTransform, operacja</span><span class="sxs-lookup"><span data-stu-id="9dd02-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="9dd02-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9dd02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9dd02-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9dd02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9dd02-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji little-endian.</span><span class="sxs-lookup"><span data-stu-id="9dd02-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="9dd02-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9dd02-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="9dd02-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9dd02-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9dd02-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="9dd02-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dd02-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dd02-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9dd02-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9dd02-110">Remarks</span></span>

<span data-ttu-id="9dd02-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu little endian.</span><span class="sxs-lookup"><span data-stu-id="9dd02-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd02-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9dd02-112">See Also</span></span>

- [<span data-ttu-id="9dd02-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="9dd02-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)