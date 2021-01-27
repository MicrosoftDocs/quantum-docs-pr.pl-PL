---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852275"
---
# <a name="qftle-operation"></a><span data-ttu-id="a554d-102">QFTLE, operacja</span><span class="sxs-lookup"><span data-stu-id="a554d-102">QFTLE operation</span></span>

<span data-ttu-id="a554d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a554d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a554d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a554d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a554d-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji little-endian.</span><span class="sxs-lookup"><span data-stu-id="a554d-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a554d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a554d-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="a554d-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a554d-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a554d-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="a554d-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="a554d-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a554d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a554d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a554d-110">Remarks</span></span>

<span data-ttu-id="a554d-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu little endian.</span><span class="sxs-lookup"><span data-stu-id="a554d-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="a554d-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a554d-112">See Also</span></span>

- [<span data-ttu-id="a554d-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="a554d-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)