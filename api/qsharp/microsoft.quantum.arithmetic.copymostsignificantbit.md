---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843265"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="ce6e3-102">CopyMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="ce6e3-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="ce6e3-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ce6e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ce6e3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce6e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce6e3-105">Kopiuje najbardziej znaczący bit rejestru qubit `from` reprezentujący liczbę całkowitą bez znaku w qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="ce6e3-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ce6e3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ce6e3-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="ce6e3-107">z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ce6e3-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ce6e3-108">Liczba całkowita bez znaku, z której jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="ce6e3-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="ce6e3-109">Liczba całkowita jest zakodowana w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="ce6e3-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ce6e3-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ce6e3-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ce6e3-111">Qubit, w którym jest kopiowany najwyższy bit.</span><span class="sxs-lookup"><span data-stu-id="ce6e3-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="ce6e3-112">Kodowanie bitowe jest w obliczeniach.</span><span class="sxs-lookup"><span data-stu-id="ce6e3-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce6e3-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce6e3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ce6e3-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ce6e3-114">See Also</span></span>

- [<span data-ttu-id="ce6e3-115">Microsoft. Quantum. arytmetyczne. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="ce6e3-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)