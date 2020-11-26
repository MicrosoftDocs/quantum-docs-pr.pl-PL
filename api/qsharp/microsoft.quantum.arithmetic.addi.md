---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191027"
---
# <a name="addi-operation"></a><span data-ttu-id="55120-102">AddI, operacja</span><span class="sxs-lookup"><span data-stu-id="55120-102">AddI operation</span></span>

<span data-ttu-id="55120-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="55120-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="55120-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="55120-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="55120-105">Program automatycznie wybiera między dodawaniem i bez, w zależności od rozmiaru rejestru `ys` .</span><span class="sxs-lookup"><span data-stu-id="55120-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="55120-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="55120-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="55120-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="55120-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="55120-108">$n $-bitowy składnik dodawania.</span><span class="sxs-lookup"><span data-stu-id="55120-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="55120-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="55120-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="55120-110">Składnik dodawania z co najmniej $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="55120-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="55120-111">Będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="55120-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55120-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55120-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

