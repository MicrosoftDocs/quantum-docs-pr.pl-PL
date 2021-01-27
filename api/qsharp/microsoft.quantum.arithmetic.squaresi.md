---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842923"
---
# <a name="squaresi-operation"></a><span data-ttu-id="62c06-102">SquareSI, operacja</span><span class="sxs-lookup"><span data-stu-id="62c06-102">SquareSI operation</span></span>

<span data-ttu-id="62c06-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62c06-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62c06-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="62c06-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="62c06-105">Kwadratowa liczba całkowita ze znakiem `xs` i przechowywanie wyniku `result` , który musi być początkowy od zera.</span><span class="sxs-lookup"><span data-stu-id="62c06-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="62c06-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="62c06-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="62c06-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62c06-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62c06-108">n-bitowa liczba całkowita do kwadratu (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62c06-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="62c06-109">wynik: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62c06-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62c06-110">wynik 2n-bitowy (SignedLittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="62c06-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62c06-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62c06-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62c06-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="62c06-112">Remarks</span></span>

<span data-ttu-id="62c06-113">Implementacja opiera się na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="62c06-113">The implementation relies on IntegerSquare.</span></span>