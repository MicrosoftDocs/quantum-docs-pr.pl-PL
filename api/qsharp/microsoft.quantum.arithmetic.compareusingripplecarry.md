---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721272"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="d7870-102">CompareUsingRippleCarry, operacja</span><span class="sxs-lookup"><span data-stu-id="d7870-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="d7870-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7870-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7870-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7870-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7870-105">Ta operacja sprawdza, czy liczba całkowita reprezentowana przez rejestr qubits jest większa niż inna liczba całkowita, stosując XOR wyniku do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="d7870-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d7870-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d7870-106">Description</span></span>

<span data-ttu-id="d7870-107">Dwie liczby całkowite `x` i `y` zapisane w rejestrach qubit o równym rozmiarze są sprawdzane, czy są one spełnione `x > y` .</span><span class="sxs-lookup"><span data-stu-id="d7870-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="d7870-108">W przypadku wartości true wartość 1 jest XORed do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="d7870-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="d7870-109">W przeciwnym razie wartość 0 jest XORed do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="d7870-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="d7870-110">Innymi słowy, ta operacja może być reprezentowana przez jednostkę $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="d7870-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="d7870-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d7870-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d7870-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d7870-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="d7870-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7870-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7870-114">Pierwszy numer, który ma być porównywany w `LittleEndian` formacie w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="d7870-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="d7870-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7870-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7870-116">Druga liczba do porównania przechowywanych w `LittleEndian` formacie w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="d7870-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="d7870-117">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d7870-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d7870-118">Qubit, który przechowuje wynik porównania $x>y $.</span><span class="sxs-lookup"><span data-stu-id="d7870-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7870-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7870-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d7870-120">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="d7870-120">References</span></span>

- <span data-ttu-id="d7870-121">Nowy program Quantum Ripple — przeniesienie obwodu dodawania Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="d7870-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>