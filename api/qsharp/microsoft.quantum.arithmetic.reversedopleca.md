---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845747"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="20f2d-102">ReversedOpLECA, funkcja</span><span class="sxs-lookup"><span data-stu-id="20f2d-102">ReversedOpLECA function</span></span>

<span data-ttu-id="20f2d-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="20f2d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="20f2d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20f2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20f2d-105">Po wykonaniu operacji pobierającej dane wejściowe o rozmiarze little-endian funkcja zwraca nową operację, która pobiera dane wejściowe big-endian.</span><span class="sxs-lookup"><span data-stu-id="20f2d-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="20f2d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="20f2d-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="20f2d-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="20f2d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="20f2d-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="20f2d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="20f2d-109">Output: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="20f2d-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="20f2d-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr big-endian.</span><span class="sxs-lookup"><span data-stu-id="20f2d-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="20f2d-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="20f2d-111">See Also</span></span>

- [<span data-ttu-id="20f2d-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="20f2d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="20f2d-113">Microsoft. Quantum. arytmetyczne. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="20f2d-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="20f2d-114">Microsoft. Quantum. arytmetyczne. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="20f2d-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="20f2d-115">Microsoft. Quantum. arytmetyczne. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="20f2d-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)