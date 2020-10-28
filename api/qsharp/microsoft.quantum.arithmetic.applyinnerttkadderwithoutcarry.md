---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721644"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="c70d8-102">ApplyInnerTTKAdderWithoutCarry, operacja</span><span class="sxs-lookup"><span data-stu-id="c70d8-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="c70d8-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c70d8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c70d8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c70d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c70d8-105">Implementuje wewnętrzną funkcję dodawania dla operacji RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="c70d8-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="c70d8-106">Jest to operacja wewnętrzna, która jest sprzężona z zewnętrzną operacją do konstruowania pełnego dodającego.</span><span class="sxs-lookup"><span data-stu-id="c70d8-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c70d8-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c70d8-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c70d8-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c70d8-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c70d8-109">LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="c70d8-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c70d8-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c70d8-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c70d8-111">LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="c70d8-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c70d8-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c70d8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c70d8-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c70d8-113">Remarks</span></span>

<span data-ttu-id="c70d8-114">Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="c70d8-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="c70d8-115">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="c70d8-115">References</span></span>

- <span data-ttu-id="c70d8-116">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="c70d8-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530