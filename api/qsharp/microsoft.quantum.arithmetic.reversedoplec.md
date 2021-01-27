---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 2dc6a596970f909af9c329dbe7002c165854cfec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846380"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="256e7-102">ReversedOpLEC, funkcja</span><span class="sxs-lookup"><span data-stu-id="256e7-102">ReversedOpLEC function</span></span>

<span data-ttu-id="256e7-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="256e7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="256e7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="256e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="256e7-105">Po wykonaniu operacji pobierającej dane wejściowe o rozmiarze little-endian funkcja zwraca nową operację, która pobiera dane wejściowe big-endian.</span><span class="sxs-lookup"><span data-stu-id="256e7-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="256e7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="256e7-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="256e7-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="256e7-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="256e7-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="256e7-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="256e7-109">Output: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to CTL</span><span class="sxs-lookup"><span data-stu-id="256e7-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="256e7-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr big-endian.</span><span class="sxs-lookup"><span data-stu-id="256e7-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="256e7-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="256e7-111">See Also</span></span>

- [<span data-ttu-id="256e7-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="256e7-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="256e7-113">Microsoft. Quantum. arytmetyczne. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="256e7-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="256e7-114">Microsoft. Quantum. arytmetyczne. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="256e7-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="256e7-115">Microsoft. Quantum. arytmetyczne. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="256e7-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)