---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 0e131204d3eaff7f99aa9ff7c3c1ae93a1bf611b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846343"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="3f97a-102">RippleCarryAdderNoCarryTTK, operacja</span><span class="sxs-lookup"><span data-stu-id="3f97a-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="3f97a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f97a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f97a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f97a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f97a-105">Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych bez przeprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="3f97a-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3f97a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3f97a-106">Description</span></span>

<span data-ttu-id="3f97a-107">W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , operacja oblicza sumę dwóch liczb całkowitych modulo $2 ^ n $, gdzie $n $ jest rozmiarem bitowym danych wejściowych `xs` i `ys` .</span><span class="sxs-lookup"><span data-stu-id="3f97a-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="3f97a-108">Nie jest obliczany bit przeprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="3f97a-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="3f97a-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3f97a-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3f97a-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f97a-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f97a-111">LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.</span><span class="sxs-lookup"><span data-stu-id="3f97a-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="3f97a-112">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f97a-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f97a-113">LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, jest modyfikowany do przechowywania $n $ najmniej znaczących bitów sum.</span><span class="sxs-lookup"><span data-stu-id="3f97a-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f97a-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f97a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3f97a-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3f97a-115">Remarks</span></span>

<span data-ttu-id="3f97a-116">Ta operacja ma takie same funkcje jak RippleCarryAdderTTK, ale nie zwraca bitu przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="3f97a-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="3f97a-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="3f97a-117">References</span></span>

- <span data-ttu-id="3f97a-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="3f97a-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530