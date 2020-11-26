---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205579"
---
# <a name="qftle-operation"></a><span data-ttu-id="236d8-102">QFTLE, operacja</span><span class="sxs-lookup"><span data-stu-id="236d8-102">QFTLE operation</span></span>

<span data-ttu-id="236d8-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="236d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="236d8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="236d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="236d8-105">Wykonuje transformację Quantum Fouriera na rejestrze Quantum zawierającym liczbę całkowitą w reprezentacji little-endian.</span><span class="sxs-lookup"><span data-stu-id="236d8-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="236d8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="236d8-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="236d8-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="236d8-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="236d8-108">Rejestr Quantum, do którego zastosowano transformację Quantum Fouriera</span><span class="sxs-lookup"><span data-stu-id="236d8-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="236d8-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="236d8-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="236d8-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="236d8-110">Remarks</span></span>

<span data-ttu-id="236d8-111">Przyjmuje się, że dane wejściowe i wyjściowe są w kodowaniu little endian.</span><span class="sxs-lookup"><span data-stu-id="236d8-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="236d8-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="236d8-112">See Also</span></span>

- [<span data-ttu-id="236d8-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="236d8-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)