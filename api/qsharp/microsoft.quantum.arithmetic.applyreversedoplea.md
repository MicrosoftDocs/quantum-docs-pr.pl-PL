---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 073ba908f2a06d36a8b73237f6a12d974b9d4d15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721452"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="8016f-102">ApplyReversedOpLEA, operacja</span><span class="sxs-lookup"><span data-stu-id="8016f-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="8016f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8016f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8016f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8016f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8016f-105">Stosuje operację, która powoduje, że dane wejściowe w formacie big-endian są zakodowane w rejestrze, a liczba całkowita bez znaku jest używana.</span><span class="sxs-lookup"><span data-stu-id="8016f-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8016f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8016f-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="8016f-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="8016f-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8016f-108">Operacja, która działa w odniesieniu do rejestru little-endian.</span><span class="sxs-lookup"><span data-stu-id="8016f-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="8016f-109">Zarejestruj się: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="8016f-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="8016f-110">Rejestr big-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="8016f-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8016f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8016f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8016f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8016f-112">See Also</span></span>

- [<span data-ttu-id="8016f-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="8016f-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="8016f-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="8016f-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="8016f-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="8016f-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)