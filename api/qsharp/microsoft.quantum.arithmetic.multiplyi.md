---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843026"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="c9b65-102">MultiplyI, operacja</span><span class="sxs-lookup"><span data-stu-id="c9b65-102">MultiplyI operation</span></span>

<span data-ttu-id="c9b65-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c9b65-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c9b65-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c9b65-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c9b65-105">Pomnóż liczbę całkowitą `xs` przez liczbę całkowitą `ys` i Zapisz wynik w `result` , który musi być początkowy od zera.</span><span class="sxs-lookup"><span data-stu-id="c9b65-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c9b65-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c9b65-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c9b65-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b65-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c9b65-108">$n $-bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b65-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c9b65-109">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b65-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c9b65-110">mnożnik $n $-bitowy (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b65-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="c9b65-111">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b65-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c9b65-112">wynik $2n $-bit (LittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c9b65-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9b65-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9b65-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9b65-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c9b65-114">Remarks</span></span>

<span data-ttu-id="c9b65-115">Używa standardowego podejścia Shift-and-Add do implementowania mnożenia.</span><span class="sxs-lookup"><span data-stu-id="c9b65-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="c9b65-116">Kontrolowana wersja została ulepszona przez skopiowanie $x _i $ do Ancilla qubit warunku na qubits sterowania, a następnie kontrolowanie dodawania na Ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="c9b65-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>