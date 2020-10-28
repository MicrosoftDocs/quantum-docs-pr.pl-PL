---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721212"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="4b80e-102">CopyMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="4b80e-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="4b80e-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b80e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b80e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b80e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b80e-105">Kopiuje najbardziej znaczący bit rejestru qubit `from` reprezentujący liczbę całkowitą bez znaku w qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="4b80e-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4b80e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4b80e-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="4b80e-107">z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b80e-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b80e-108">Liczba całkowita bez znaku, z której jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="4b80e-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="4b80e-109">Liczba całkowita jest zakodowana w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="4b80e-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4b80e-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b80e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b80e-111">Qubit, w którym jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="4b80e-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="4b80e-112">Kodowanie bitowe jest w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="4b80e-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b80e-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b80e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4b80e-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b80e-114">See Also</span></span>

- [<span data-ttu-id="4b80e-115">Microsoft. Quantum. arytmetyczne. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="4b80e-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)