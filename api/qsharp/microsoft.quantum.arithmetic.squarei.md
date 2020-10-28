---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719541"
---
# <a name="squarei-operation"></a><span data-ttu-id="dc71e-102">SquareI, operacja</span><span class="sxs-lookup"><span data-stu-id="dc71e-102">SquareI operation</span></span>

<span data-ttu-id="dc71e-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dc71e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dc71e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc71e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc71e-105">Oblicza kwadrat liczby całkowitej `xs` w `result` , która musi być początkowo zerowa.</span><span class="sxs-lookup"><span data-stu-id="dc71e-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="dc71e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dc71e-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="dc71e-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc71e-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dc71e-108">$n $-bit Number do kwadratu (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc71e-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="dc71e-109">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc71e-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dc71e-110">wynik $2n $-bit (LittleEndian) musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="dc71e-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc71e-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc71e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc71e-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc71e-112">Remarks</span></span>

<span data-ttu-id="dc71e-113">Używa standardowej metody Shift-and-Add do obliczania kwadratu.</span><span class="sxs-lookup"><span data-stu-id="dc71e-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="dc71e-114">Zapisuje $n-$1 qubits w porównaniu do rozwiązania prostego przesyłania dalej, które najpierw kopiuje wyjście XS przed zastosowaniem zwykłego mnożnika, a następnie cofa operację kopiowania.</span><span class="sxs-lookup"><span data-stu-id="dc71e-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>