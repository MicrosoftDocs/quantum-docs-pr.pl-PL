---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 0674567f5d45890aa2f631b2e0e4d75d20a72449
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846453"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="1a263-102">ReversedOpBEC, funkcja</span><span class="sxs-lookup"><span data-stu-id="1a263-102">ReversedOpBEC function</span></span>

<span data-ttu-id="1a263-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1a263-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1a263-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a263-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a263-105">W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.</span><span class="sxs-lookup"><span data-stu-id="1a263-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="1a263-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1a263-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="1a263-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="1a263-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1a263-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="1a263-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-ctl"></a><span data-ttu-id="1a263-109">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to CTL</span><span class="sxs-lookup"><span data-stu-id="1a263-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1a263-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.</span><span class="sxs-lookup"><span data-stu-id="1a263-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a263-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1a263-111">See Also</span></span>

- [<span data-ttu-id="1a263-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="1a263-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="1a263-113">Microsoft. Quantum. arytmetyczne. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="1a263-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="1a263-114">Microsoft. Quantum. arytmetyczne. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="1a263-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="1a263-115">Microsoft. Quantum. arytmetyczne. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="1a263-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)