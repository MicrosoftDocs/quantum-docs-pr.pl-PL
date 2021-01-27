---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846482"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="02224-102">ReversedOpBE, funkcja</span><span class="sxs-lookup"><span data-stu-id="02224-102">ReversedOpBE function</span></span>

<span data-ttu-id="02224-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="02224-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="02224-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02224-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02224-105">W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.</span><span class="sxs-lookup"><span data-stu-id="02224-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="02224-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="02224-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="02224-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02224-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="02224-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="02224-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="02224-109">Dane wyjściowe [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) : => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="02224-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="02224-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.</span><span class="sxs-lookup"><span data-stu-id="02224-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="02224-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02224-111">See Also</span></span>

- [<span data-ttu-id="02224-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="02224-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="02224-113">Microsoft. Quantum. arytmetyczne. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="02224-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="02224-114">Microsoft. Quantum. arytmetyczne. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="02224-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="02224-115">Microsoft. Quantum. arytmetyczne. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="02224-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)