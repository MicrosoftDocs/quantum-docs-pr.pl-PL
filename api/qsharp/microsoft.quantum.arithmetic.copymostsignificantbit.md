---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223293"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="4d349-102">CopyMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="4d349-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="4d349-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4d349-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4d349-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d349-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d349-105">Kopiuje najbardziej znaczący bit rejestru qubit `from` reprezentujący liczbę całkowitą bez znaku w qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="4d349-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4d349-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4d349-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="4d349-107">z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4d349-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4d349-108">Liczba całkowita bez znaku, z której jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="4d349-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="4d349-109">Liczba całkowita jest zakodowana w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="4d349-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4d349-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4d349-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4d349-111">Qubit, w którym jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="4d349-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="4d349-112">Kodowanie bitowe jest w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="4d349-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d349-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d349-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4d349-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4d349-114">See Also</span></span>

- [<span data-ttu-id="4d349-115">Microsoft. Quantum. arytmetyczne. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="4d349-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)