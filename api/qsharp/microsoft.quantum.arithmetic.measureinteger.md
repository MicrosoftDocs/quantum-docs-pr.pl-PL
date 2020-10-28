---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720969"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="5d5cd-102">MeasureInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="5d5cd-102">MeasureInteger operation</span></span>

<span data-ttu-id="5d5cd-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5d5cd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5d5cd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d5cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d5cd-105">Mierzy zawartość rejestru Quantum i konwertuje ją na liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="5d5cd-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="5d5cd-106">Pomiary są wykonywane w odniesieniu do standardowej obliczeń, tj. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="5d5cd-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="5d5cd-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5d5cd-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="5d5cd-108">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5d5cd-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5d5cd-109">Rejestr Quantum w kodowaniu little-endian.</span><span class="sxs-lookup"><span data-stu-id="5d5cd-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="5d5cd-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d5cd-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d5cd-111">Liczba całkowita bez znaku, która zawiera mierzoną wartość `target` .</span><span class="sxs-lookup"><span data-stu-id="5d5cd-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d5cd-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5d5cd-112">Remarks</span></span>

<span data-ttu-id="5d5cd-113">Ta operacja resetuje swój rejestr wejściowy do stanu $ \ket{00\cdots 0} $, który jest odpowiedni do wydawania z powrotem do maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="5d5cd-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d5cd-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5d5cd-114">See Also</span></span>

- [<span data-ttu-id="5d5cd-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="5d5cd-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)