---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721137"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="f9e81-102">GreaterThan, operacja</span><span class="sxs-lookup"><span data-stu-id="f9e81-102">GreaterThan operation</span></span>

<span data-ttu-id="f9e81-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f9e81-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f9e81-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9e81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9e81-105">Stosuje większe niż porównanie dwóch liczb całkowitych zakodowanych w rejestrach qubit, przerzucając docelowy qubit na podstawie wyniku porównania.</span><span class="sxs-lookup"><span data-stu-id="f9e81-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="f9e81-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f9e81-106">Description</span></span>

<span data-ttu-id="f9e81-107">Wykonuje ściśle większe niż porównanie dwóch liczb całkowitych, $x $ i $y $, zakodowane w qubit rejestruje i YS.</span><span class="sxs-lookup"><span data-stu-id="f9e81-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="f9e81-108">Jeśli $x > y $, wynik qubit zostanie przerzucony, w przeciwnym razie wynik qubit spowoduje zachowanie stanu.</span><span class="sxs-lookup"><span data-stu-id="f9e81-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="f9e81-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f9e81-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f9e81-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9e81-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9e81-111">LittleEndian qubit Zarejestruj pierwszą liczbę całkowitą $x $.</span><span class="sxs-lookup"><span data-stu-id="f9e81-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f9e81-112">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9e81-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9e81-113">LittleEndian qubit Register kodowanie drugiej liczby całkowitej $y $.</span><span class="sxs-lookup"><span data-stu-id="f9e81-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="f9e81-114">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9e81-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9e81-115">Pojedyncze qubit, które zostaną przerzucone, jeśli $x > y $.</span><span class="sxs-lookup"><span data-stu-id="f9e81-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9e81-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9e81-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f9e81-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9e81-117">Remarks</span></span>

<span data-ttu-id="f9e81-118">Używa lew, która $x-y = (x ' + y) ' $, gdzie ' oznacza uzupełnienie jednego.</span><span class="sxs-lookup"><span data-stu-id="f9e81-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="f9e81-119">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="f9e81-119">References</span></span>

- <span data-ttu-id="f9e81-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.</span><span class="sxs-lookup"><span data-stu-id="f9e81-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="f9e81-121">Thomas Haener, Martin Roetteler, krysta M. Svore: "factoring using 2n + 2 qubits with modułowe mnożenia", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="f9e81-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>