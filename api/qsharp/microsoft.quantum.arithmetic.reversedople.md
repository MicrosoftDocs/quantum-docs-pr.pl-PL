---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846395"
---
# <a name="reversedople-function"></a><span data-ttu-id="4dcdd-102">ReversedOpLE, funkcja</span><span class="sxs-lookup"><span data-stu-id="4dcdd-102">ReversedOpLE function</span></span>

<span data-ttu-id="4dcdd-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4dcdd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4dcdd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4dcdd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4dcdd-105">Po wykonaniu operacji pobierającej dane wejściowe o rozmiarze little-endian funkcja zwraca nową operację, która pobiera dane wejściowe big-endian.</span><span class="sxs-lookup"><span data-stu-id="4dcdd-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="4dcdd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4dcdd-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="4dcdd-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dcdd-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dcdd-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="4dcdd-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="4dcdd-109">Dane wyjściowe [](xref:Microsoft.Quantum.Arithmetic.BigEndian) : => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian</span><span class="sxs-lookup"><span data-stu-id="4dcdd-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dcdd-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr big-endian.</span><span class="sxs-lookup"><span data-stu-id="4dcdd-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dcdd-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4dcdd-111">See Also</span></span>

- [<span data-ttu-id="4dcdd-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="4dcdd-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="4dcdd-113">Microsoft. Quantum. arytmetyczne. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="4dcdd-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="4dcdd-114">Microsoft. Quantum. arytmetyczne. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="4dcdd-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="4dcdd-115">Microsoft. Quantum. arytmetyczne. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="4dcdd-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)