---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223480"
---
# <a name="comparegti-operation"></a><span data-ttu-id="3f48b-102">CompareGTI, operacja</span><span class="sxs-lookup"><span data-stu-id="3f48b-102">CompareGTI operation</span></span>

<span data-ttu-id="3f48b-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f48b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f48b-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3f48b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3f48b-105">Otoka dla porównania liczb całkowitych: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="3f48b-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3f48b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3f48b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3f48b-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f48b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f48b-108">Numer pierwszej $n $-bitowy</span><span class="sxs-lookup"><span data-stu-id="3f48b-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="3f48b-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f48b-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f48b-110">Druga $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="3f48b-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="3f48b-111">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3f48b-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3f48b-112">Zostanie przerzucony, jeśli $x > y $</span><span class="sxs-lookup"><span data-stu-id="3f48b-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f48b-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f48b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

