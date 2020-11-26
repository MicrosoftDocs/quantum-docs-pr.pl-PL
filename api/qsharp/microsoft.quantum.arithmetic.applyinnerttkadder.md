---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 1de0248066aec531d78130703414067603ffd34d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191010"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="f7cdb-102">ApplyInnerTTKAdder, operacja</span><span class="sxs-lookup"><span data-stu-id="f7cdb-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="f7cdb-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f7cdb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7cdb-105">Implementuje wewnętrzną funkcję dodawania dla operacji RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="f7cdb-106">Jest to operacja wewnętrzna, która jest sprzężona z zewnętrzną operacją do konstruowania pełnego dodającego.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f7cdb-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f7cdb-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f7cdb-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7cdb-109">LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f7cdb-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7cdb-111">LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="f7cdb-112">Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7cdb-113">Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7cdb-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7cdb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7cdb-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f7cdb-115">Remarks</span></span>

<span data-ttu-id="f7cdb-116">Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="f7cdb-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="f7cdb-117">References</span></span>

- <span data-ttu-id="f7cdb-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="f7cdb-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530