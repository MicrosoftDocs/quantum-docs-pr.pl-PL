---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843120"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="234f0-102">MeasureInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="234f0-102">MeasureInteger operation</span></span>

<span data-ttu-id="234f0-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="234f0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="234f0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="234f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="234f0-105">Mierzy zawartość rejestru Quantum i konwertuje ją na liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="234f0-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="234f0-106">Pomiary są wykonywane w odniesieniu do standardowej obliczeń, tj. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="234f0-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="234f0-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="234f0-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="234f0-108">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="234f0-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="234f0-109">Rejestr Quantum w kodowaniu little-endian.</span><span class="sxs-lookup"><span data-stu-id="234f0-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="234f0-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="234f0-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="234f0-111">Liczba całkowita bez znaku, która zawiera mierzoną wartość `target` .</span><span class="sxs-lookup"><span data-stu-id="234f0-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="234f0-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="234f0-112">Remarks</span></span>

<span data-ttu-id="234f0-113">Ta operacja resetuje swój rejestr wejściowy do stanu $ \ket{00\cdots 0} $, który jest odpowiedni do wydawania z powrotem do maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="234f0-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="234f0-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="234f0-114">See Also</span></span>

- [<span data-ttu-id="234f0-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="234f0-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)