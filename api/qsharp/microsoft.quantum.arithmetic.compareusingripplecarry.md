---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843288"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="534e6-102">CompareUsingRippleCarry, operacja</span><span class="sxs-lookup"><span data-stu-id="534e6-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="534e6-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="534e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="534e6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="534e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="534e6-105">Ta operacja sprawdza, czy liczba całkowita reprezentowana przez rejestr qubits jest większa niż inna liczba całkowita, stosując XOR wyniku do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="534e6-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="534e6-106">Opis</span><span class="sxs-lookup"><span data-stu-id="534e6-106">Description</span></span>

<span data-ttu-id="534e6-107">Dwie liczby całkowite `x` i `y` zapisane w rejestrach qubit o równym rozmiarze są sprawdzane, czy są one spełnione `x > y` .</span><span class="sxs-lookup"><span data-stu-id="534e6-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="534e6-108">W przypadku wartości true wartość 1 jest XORed do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="534e6-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="534e6-109">W przeciwnym razie wartość 0 jest XORed do qubit wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="534e6-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="534e6-110">Innymi słowy, ta operacja może być reprezentowana przez jednostkę $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="534e6-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="534e6-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="534e6-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="534e6-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="534e6-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="534e6-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="534e6-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="534e6-114">Pierwszy numer, który ma być porównywany w `LittleEndian` formacie w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="534e6-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="534e6-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="534e6-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="534e6-116">Druga liczba do porównania przechowywanych w `LittleEndian` formacie w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="534e6-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="534e6-117">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="534e6-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="534e6-118">Qubit, który przechowuje wynik porównania $x>y $.</span><span class="sxs-lookup"><span data-stu-id="534e6-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="534e6-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="534e6-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="534e6-120">Odwołania</span><span class="sxs-lookup"><span data-stu-id="534e6-120">References</span></span>

- <span data-ttu-id="534e6-121">Nowy program Quantum Ripple — przeniesienie obwodu dodawania Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="534e6-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>