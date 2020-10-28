---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717789"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="b6785-102">ApplyQuantumFourierTransformBE, operacja</span><span class="sxs-lookup"><span data-stu-id="b6785-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="b6785-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6785-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6785-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6785-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6785-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji big-endian.</span><span class="sxs-lookup"><span data-stu-id="b6785-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b6785-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b6785-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="b6785-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="b6785-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="b6785-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="b6785-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6785-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6785-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6785-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b6785-110">Remarks</span></span>

<span data-ttu-id="b6785-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu big endian.</span><span class="sxs-lookup"><span data-stu-id="b6785-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6785-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b6785-112">See Also</span></span>

- [<span data-ttu-id="b6785-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="b6785-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="b6785-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="b6785-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)