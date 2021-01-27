---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841564"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="643c2-102">ApplyQuantumFourierTransformBE, operacja</span><span class="sxs-lookup"><span data-stu-id="643c2-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="643c2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="643c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="643c2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="643c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="643c2-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji big-endian.</span><span class="sxs-lookup"><span data-stu-id="643c2-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="643c2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="643c2-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="643c2-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="643c2-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="643c2-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="643c2-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="643c2-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="643c2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="643c2-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="643c2-110">Remarks</span></span>

<span data-ttu-id="643c2-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu big endian.</span><span class="sxs-lookup"><span data-stu-id="643c2-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="643c2-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="643c2-112">See Also</span></span>

- [<span data-ttu-id="643c2-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="643c2-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="643c2-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="643c2-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)