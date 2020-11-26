---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 3a5fef3bb4549433540b2a7b5e94d3cd2d527639
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202774"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="68969-102">ApplyReversedOpBEC, operacja</span><span class="sxs-lookup"><span data-stu-id="68969-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="68969-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="68969-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="68969-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68969-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68969-105">Stosuje operację, która pobiera dane wejściowe big-endian do rejestru kodowania liczby całkowitej bez znaku przy użyciu formatu little-endian.</span><span class="sxs-lookup"><span data-stu-id="68969-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="68969-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="68969-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="68969-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="68969-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="68969-108">Operacja, która działa w przypadku rejestracji big-endian.</span><span class="sxs-lookup"><span data-stu-id="68969-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="68969-109">Zarejestruj się: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="68969-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="68969-110">Rejestr little-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="68969-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="68969-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68969-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="68969-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="68969-112">See Also</span></span>

- [<span data-ttu-id="68969-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="68969-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="68969-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="68969-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="68969-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="68969-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)