---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: f606011dd002d6eadc4f882005f4577aeb28cac0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721485"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="6fb1f-102">ApplyReversedOpBEA, operacja</span><span class="sxs-lookup"><span data-stu-id="6fb1f-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="6fb1f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6fb1f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6fb1f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fb1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fb1f-105">Stosuje operację, która pobiera dane wejściowe big-endian do rejestru kodowania liczby całkowitej bez znaku przy użyciu formatu little-endian.</span><span class="sxs-lookup"><span data-stu-id="6fb1f-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6fb1f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6fb1f-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="6fb1f-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) BigEndian</span><span class="sxs-lookup"><span data-stu-id="6fb1f-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6fb1f-108">Operacja, która działa w przypadku rejestracji big-endian.</span><span class="sxs-lookup"><span data-stu-id="6fb1f-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="6fb1f-109">Zarejestruj się: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fb1f-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fb1f-110">Rejestr little-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="6fb1f-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fb1f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fb1f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6fb1f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6fb1f-112">See Also</span></span>

- [<span data-ttu-id="6fb1f-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="6fb1f-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="6fb1f-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="6fb1f-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="6fb1f-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="6fb1f-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)