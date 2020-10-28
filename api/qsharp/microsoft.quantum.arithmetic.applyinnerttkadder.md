---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721656"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="d0ab5-102">ApplyInnerTTKAdder, operacja</span><span class="sxs-lookup"><span data-stu-id="d0ab5-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="d0ab5-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d0ab5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0ab5-105">Implementuje wewnętrzną funkcję dodawania dla operacji RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="d0ab5-106">Jest to operacja wewnętrzna, która jest sprzężona z zewnętrzną operacją do konstruowania pełnego dodającego.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d0ab5-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d0ab5-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d0ab5-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d0ab5-109">LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d0ab5-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d0ab5-111">LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="d0ab5-112">Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0ab5-113">Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0ab5-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0ab5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0ab5-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0ab5-115">Remarks</span></span>

<span data-ttu-id="d0ab5-116">Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="d0ab5-117">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="d0ab5-117">References</span></span>

- <span data-ttu-id="d0ab5-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="d0ab5-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530