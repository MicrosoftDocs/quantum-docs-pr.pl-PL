---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190619"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="aa724-102">ApplyOuterTTKAdder, operacja</span><span class="sxs-lookup"><span data-stu-id="aa724-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="aa724-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa724-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa724-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa724-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa724-105">Implementuje operację zewnętrzną dla RippleCarryAdderTTK, aby koniugat operacji wewnętrznej w celu skonstruowania pełnego dodającego.</span><span class="sxs-lookup"><span data-stu-id="aa724-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aa724-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa724-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="aa724-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa724-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa724-108">LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="aa724-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="aa724-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa724-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa724-110">LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="aa724-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa724-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa724-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="aa724-112">Odwołania</span><span class="sxs-lookup"><span data-stu-id="aa724-112">References</span></span>

- <span data-ttu-id="aa724-113">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="aa724-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530