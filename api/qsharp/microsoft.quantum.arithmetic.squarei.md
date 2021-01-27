---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846311"
---
# <a name="squarei-operation"></a><span data-ttu-id="a4193-102">SquareI, operacja</span><span class="sxs-lookup"><span data-stu-id="a4193-102">SquareI operation</span></span>

<span data-ttu-id="a4193-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a4193-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a4193-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a4193-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a4193-105">Oblicza kwadrat liczby całkowitej `xs` w `result` , która musi być początkowo zerowa.</span><span class="sxs-lookup"><span data-stu-id="a4193-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a4193-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a4193-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a4193-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4193-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a4193-108">$n $-bit Number do kwadratu (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4193-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="a4193-109">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4193-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a4193-110">wynik $2n $-bit (LittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a4193-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4193-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4193-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4193-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a4193-112">Remarks</span></span>

<span data-ttu-id="a4193-113">Używa standardowej metody Shift-and-Add do obliczania kwadratu.</span><span class="sxs-lookup"><span data-stu-id="a4193-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="a4193-114">Zapisuje $n-$1 qubits w porównaniu do rozwiązania prostego przesyłania dalej, które najpierw kopiuje wyjście XS przed zastosowaniem zwykłego mnożnika, a następnie cofa operację kopiowania.</span><span class="sxs-lookup"><span data-stu-id="a4193-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>