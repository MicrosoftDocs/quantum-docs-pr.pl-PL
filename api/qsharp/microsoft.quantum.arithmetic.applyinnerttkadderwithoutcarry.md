---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190959"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="38e50-102">ApplyInnerTTKAdderWithoutCarry, operacja</span><span class="sxs-lookup"><span data-stu-id="38e50-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="38e50-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="38e50-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="38e50-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38e50-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38e50-105">Implementuje wewnętrzną funkcję dodawania dla operacji RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="38e50-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="38e50-106">Jest to operacja wewnętrzna, która jest sprzężona z zewnętrzną operacją do konstruowania pełnego dodającego.</span><span class="sxs-lookup"><span data-stu-id="38e50-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="38e50-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="38e50-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="38e50-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="38e50-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="38e50-109">LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="38e50-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="38e50-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="38e50-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="38e50-111">LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="38e50-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38e50-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38e50-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="38e50-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="38e50-113">Remarks</span></span>

<span data-ttu-id="38e50-114">Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="38e50-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="38e50-115">Odwołania</span><span class="sxs-lookup"><span data-stu-id="38e50-115">References</span></span>

- <span data-ttu-id="38e50-116">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="38e50-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530