---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846359"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="ad40e-102">RippleCarryAdderCDKM, operacja</span><span class="sxs-lookup"><span data-stu-id="ad40e-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="ad40e-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ad40e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ad40e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad40e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad40e-105">Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="ad40e-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ad40e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ad40e-106">Description</span></span>

<span data-ttu-id="ad40e-107">W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , a qubit, operacja oblicza sumę dwóch liczb całkowitych, w których $n $ najmniej znaczące bity wyniku są przechowywane, `ys` a bit przeprowadzenia jest XORed do qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="ad40e-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="ad40e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ad40e-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ad40e-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad40e-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad40e-110">LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.</span><span class="sxs-lookup"><span data-stu-id="ad40e-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ad40e-111">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad40e-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad40e-112">LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, został zmodyfikowany w celu przechowywania n najmniej znaczących bitów sum.</span><span class="sxs-lookup"><span data-stu-id="ad40e-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="ad40e-113">Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ad40e-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ad40e-114">Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.</span><span class="sxs-lookup"><span data-stu-id="ad40e-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad40e-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad40e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ad40e-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ad40e-116">Remarks</span></span>

<span data-ttu-id="ad40e-117">Ta operacja ma takie same funkcje jak RippleCarryAdderD, ale używa tylko jednej pomocniczej qubit zamiast $n $.</span><span class="sxs-lookup"><span data-stu-id="ad40e-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="ad40e-118">Odwołania</span><span class="sxs-lookup"><span data-stu-id="ad40e-118">References</span></span>

- <span data-ttu-id="ad40e-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.</span><span class="sxs-lookup"><span data-stu-id="ad40e-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1