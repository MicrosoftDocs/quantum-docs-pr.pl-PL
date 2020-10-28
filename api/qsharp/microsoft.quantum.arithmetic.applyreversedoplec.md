---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721449"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="de6af-102">ApplyReversedOpLEC, operacja</span><span class="sxs-lookup"><span data-stu-id="de6af-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="de6af-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de6af-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de6af-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de6af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de6af-105">Stosuje operację, która powoduje, że dane wejściowe w formacie big-endian są zakodowane w rejestrze, a liczba całkowita bez znaku jest używana.</span><span class="sxs-lookup"><span data-stu-id="de6af-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="de6af-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="de6af-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="de6af-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="de6af-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="de6af-108">Operacja, która działa w odniesieniu do rejestru little-endian.</span><span class="sxs-lookup"><span data-stu-id="de6af-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="de6af-109">Zarejestruj się: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="de6af-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="de6af-110">Rejestr big-endian do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="de6af-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de6af-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de6af-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="de6af-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de6af-112">See Also</span></span>

- [<span data-ttu-id="de6af-113">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="de6af-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="de6af-114">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="de6af-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="de6af-115">Microsoft. Quantum. arytmetyczne. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="de6af-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)