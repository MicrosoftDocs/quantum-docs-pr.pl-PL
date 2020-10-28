---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721476"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="010be-102">ApplyReversedOpBEC, operacja</span><span class="sxs-lookup"><span data-stu-id="010be-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="010be-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="010be-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="010be-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="010be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="010be-105">Stosuje operację, która pobiera dane wejściowe big-endian do rejestru kodowania liczby całkowitej bez znaku przy użyciu formatu little-endian.</span><span class="sxs-lookup"><span data-stu-id="010be-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="010be-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="010be-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="010be-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="010be-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="010be-108">Operacja, która działa w przypadku rejestracji big-endian.</span><span class="sxs-lookup"><span data-stu-id="010be-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="010be-109">Zarejestruj się: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="010be-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="010be-110">Rejestr little-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="010be-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="010be-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="010be-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="010be-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="010be-112">See Also</span></span>

- [<span data-ttu-id="010be-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="010be-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="010be-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="010be-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="010be-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="010be-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)