---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: b87c8f25acc8854d5e8d28f58cfc99dffb92a973
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222120"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="ca0e5-102">RippleCarryAdderD, operacja</span><span class="sxs-lookup"><span data-stu-id="ca0e5-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="ca0e5-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ca0e5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca0e5-105">Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="ca0e5-106">W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , a qubit, operacja oblicza sumę dwóch liczb całkowitych, w których $n $ najmniej znaczące bity wyniku są przechowywane, `ys` a bit przeprowadzenia jest XORed do qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="ca0e5-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ca0e5-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca0e5-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ca0e5-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ca0e5-109">LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ca0e5-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ca0e5-111">LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, jest modyfikowany do przechowywania $n $ najmniej znaczących bitów sum.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="ca0e5-112">Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ca0e5-113">Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca0e5-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca0e5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ca0e5-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ca0e5-115">Remarks</span></span>

<span data-ttu-id="ca0e5-116">Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="ca0e5-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="ca0e5-117">References</span></span>

- <span data-ttu-id="ca0e5-118">Thomas G. Draper: "dodanie na komputerze Quantum", 2000.</span><span class="sxs-lookup"><span data-stu-id="ca0e5-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033