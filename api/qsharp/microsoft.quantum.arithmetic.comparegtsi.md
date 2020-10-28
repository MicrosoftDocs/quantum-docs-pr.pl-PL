---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721281"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="58161-102">CompareGTSI, operacja</span><span class="sxs-lookup"><span data-stu-id="58161-102">CompareGTSI operation</span></span>

<span data-ttu-id="58161-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="58161-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="58161-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58161-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58161-105">Otoka dla porównań ze znakiem liczby całkowitej: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="58161-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="58161-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="58161-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="58161-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="58161-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="58161-108">Numer pierwszej $n $-bitowy</span><span class="sxs-lookup"><span data-stu-id="58161-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="58161-109">YS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="58161-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="58161-110">Druga $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="58161-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="58161-111">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="58161-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="58161-112">Zostanie przerzucony, jeśli $xs > YS $</span><span class="sxs-lookup"><span data-stu-id="58161-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="58161-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58161-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

