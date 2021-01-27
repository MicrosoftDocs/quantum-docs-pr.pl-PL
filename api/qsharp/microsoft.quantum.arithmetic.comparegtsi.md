---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846705"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="900ae-102">CompareGTSI, operacja</span><span class="sxs-lookup"><span data-stu-id="900ae-102">CompareGTSI operation</span></span>

<span data-ttu-id="900ae-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="900ae-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="900ae-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="900ae-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="900ae-105">Otoka dla porównań ze znakiem liczby całkowitej: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="900ae-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="900ae-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="900ae-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="900ae-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="900ae-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="900ae-108">Numer pierwszej $n $-bitowy</span><span class="sxs-lookup"><span data-stu-id="900ae-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="900ae-109">YS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="900ae-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="900ae-110">Druga $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="900ae-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="900ae-111">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="900ae-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="900ae-112">Zostanie przerzucony, jeśli $xs > YS $</span><span class="sxs-lookup"><span data-stu-id="900ae-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="900ae-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="900ae-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

