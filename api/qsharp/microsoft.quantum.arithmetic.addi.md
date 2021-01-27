---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843845"
---
# <a name="addi-operation"></a><span data-ttu-id="7c178-102">AddI, operacja</span><span class="sxs-lookup"><span data-stu-id="7c178-102">AddI operation</span></span>

<span data-ttu-id="7c178-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c178-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c178-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7c178-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7c178-105">Program automatycznie wybiera między dodawaniem i bez, w zależności od rozmiaru rejestru `ys` .</span><span class="sxs-lookup"><span data-stu-id="7c178-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c178-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7c178-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7c178-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c178-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c178-108">$n $-bitowy składnik dodawania.</span><span class="sxs-lookup"><span data-stu-id="7c178-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7c178-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c178-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c178-110">Składnik dodawania z co najmniej $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="7c178-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="7c178-111">Będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="7c178-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c178-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c178-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

