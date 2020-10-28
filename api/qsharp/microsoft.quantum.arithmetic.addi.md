---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721689"
---
# <a name="addi-operation"></a><span data-ttu-id="47fda-102">AddI, operacja</span><span class="sxs-lookup"><span data-stu-id="47fda-102">AddI operation</span></span>

<span data-ttu-id="47fda-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="47fda-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="47fda-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47fda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47fda-105">Program automatycznie wybiera między dodawaniem i bez, w zależności od rozmiaru rejestru `ys` .</span><span class="sxs-lookup"><span data-stu-id="47fda-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="47fda-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="47fda-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="47fda-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47fda-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="47fda-108">$n $-bitowy składnik dodawania.</span><span class="sxs-lookup"><span data-stu-id="47fda-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="47fda-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47fda-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="47fda-110">Składnik dodawania z co najmniej $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="47fda-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="47fda-111">Będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="47fda-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47fda-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47fda-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

