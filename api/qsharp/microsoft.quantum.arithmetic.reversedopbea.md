---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 392b97171bcfb9d35a38189fc9c27e61cf9cf7d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846471"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="eb4b6-102">ReversedOpBEA, funkcja</span><span class="sxs-lookup"><span data-stu-id="eb4b6-102">ReversedOpBEA function</span></span>

<span data-ttu-id="eb4b6-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="eb4b6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="eb4b6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb4b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb4b6-105">W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.</span><span class="sxs-lookup"><span data-stu-id="eb4b6-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="eb4b6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="eb4b6-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="eb4b6-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian jest korektą</span><span class="sxs-lookup"><span data-stu-id="eb4b6-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eb4b6-108">Operacja, której dane wejściowe mają zostać cofnięte.</span><span class="sxs-lookup"><span data-stu-id="eb4b6-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="eb4b6-109">Wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą</span><span class="sxs-lookup"><span data-stu-id="eb4b6-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eb4b6-110">Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.</span><span class="sxs-lookup"><span data-stu-id="eb4b6-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb4b6-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eb4b6-111">See Also</span></span>

- [<span data-ttu-id="eb4b6-112">Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="eb4b6-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="eb4b6-113">Microsoft. Quantum. arytmetyczne. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="eb4b6-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="eb4b6-114">Microsoft. Quantum. arytmetyczne. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="eb4b6-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="eb4b6-115">Microsoft. Quantum. arytmetyczne. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="eb4b6-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)