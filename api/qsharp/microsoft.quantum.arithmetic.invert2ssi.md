---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: 86d90fc5406089549de0036fcaebd9dc9d188c40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222851"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="6ebba-102">Invert2sSI, operacja</span><span class="sxs-lookup"><span data-stu-id="6ebba-102">Invert2sSI operation</span></span>

<span data-ttu-id="6ebba-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6ebba-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6ebba-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="6ebba-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="6ebba-105">Odwraca podaną liczbę całkowitą od 1 do 2.</span><span class="sxs-lookup"><span data-stu-id="6ebba-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6ebba-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ebba-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="6ebba-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6ebba-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6ebba-108">n-bitowa liczba całkowita ze znakiem (SignedLittleEndian), zostanie odwrócony uzupełnienie modulo 2.</span><span class="sxs-lookup"><span data-stu-id="6ebba-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ebba-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ebba-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

