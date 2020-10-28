---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719748"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="7b49b-102">MultiplySI, operacja</span><span class="sxs-lookup"><span data-stu-id="7b49b-102">MultiplySI operation</span></span>

<span data-ttu-id="7b49b-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7b49b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7b49b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b49b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b49b-105">Pomnóż liczbę całkowitą ze znakiem, `xs` która została ze znakiem liczb całkowitych `ys` i Zapisz wynik w `result` , który musi być początkowy od zera.</span><span class="sxs-lookup"><span data-stu-id="7b49b-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7b49b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7b49b-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="7b49b-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7b49b-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7b49b-108">n-bitowy multiplicand (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7b49b-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="7b49b-109">YS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7b49b-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7b49b-110">mnożnik n-bitowy (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7b49b-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="7b49b-111">wynik: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7b49b-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7b49b-112">wynik 2n-bitowy (SignedLittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="7b49b-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b49b-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b49b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

