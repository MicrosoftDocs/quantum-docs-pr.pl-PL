---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: e86a5f8586cf438189c19da75c60cfd97632dcb1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843133"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="36d71-102">Invert2sSI, operacja</span><span class="sxs-lookup"><span data-stu-id="36d71-102">Invert2sSI operation</span></span>

<span data-ttu-id="36d71-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="36d71-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="36d71-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="36d71-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="36d71-105">Odwraca podaną liczbę całkowitą od 1 do 2.</span><span class="sxs-lookup"><span data-stu-id="36d71-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="36d71-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="36d71-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="36d71-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="36d71-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="36d71-108">n-bitowa liczba całkowita ze znakiem (SignedLittleEndian), zostanie odwrócony uzupełnienie modulo 2.</span><span class="sxs-lookup"><span data-stu-id="36d71-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36d71-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36d71-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

