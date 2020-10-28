---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: ApplyReversedOpLE, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 0f73ac7d50e32f4467bc1683e421149fa38ee29a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721461"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="559c5-102">ApplyReversedOpLE, operacja</span><span class="sxs-lookup"><span data-stu-id="559c5-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="559c5-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="559c5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="559c5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="559c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="559c5-105">Stosuje operację, która powoduje, że dane wejściowe w formacie big-endian są zakodowane w rejestrze, a liczba całkowita bez znaku jest używana.</span><span class="sxs-lookup"><span data-stu-id="559c5-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="559c5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="559c5-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="559c5-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="559c5-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="559c5-108">Operacja, która działa w odniesieniu do rejestru little-endian.</span><span class="sxs-lookup"><span data-stu-id="559c5-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="559c5-109">Zarejestruj się: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="559c5-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="559c5-110">Rejestr big-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="559c5-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="559c5-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="559c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="559c5-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="559c5-112">See Also</span></span>

- [<span data-ttu-id="559c5-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="559c5-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="559c5-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="559c5-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="559c5-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="559c5-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)