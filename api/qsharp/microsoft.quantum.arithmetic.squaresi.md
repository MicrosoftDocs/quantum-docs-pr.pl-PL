---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719532"
---
# <a name="squaresi-operation"></a><span data-ttu-id="ea6a8-102">SquareSI, operacja</span><span class="sxs-lookup"><span data-stu-id="ea6a8-102">SquareSI operation</span></span>

<span data-ttu-id="ea6a8-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ea6a8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea6a8-105">Kwadratowa liczba całkowita ze znakiem `xs` i przechowywanie wyniku `result` , który musi być początkowy od zera.</span><span class="sxs-lookup"><span data-stu-id="ea6a8-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ea6a8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ea6a8-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="ea6a8-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ea6a8-108">n-bitowa liczba całkowita do kwadratu (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="ea6a8-109">wynik: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ea6a8-110">wynik 2n-bitowy (SignedLittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="ea6a8-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea6a8-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea6a8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea6a8-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ea6a8-112">Remarks</span></span>

<span data-ttu-id="ea6a8-113">Implementacja opiera się na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="ea6a8-113">The implementation relies on IntegerSquare.</span></span>