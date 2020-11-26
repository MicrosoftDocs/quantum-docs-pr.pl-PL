---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219451"
---
# <a name="zbits-function"></a><span data-ttu-id="d5fc5-102">ZBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="d5fc5-102">ZBits function</span></span>

<span data-ttu-id="d5fc5-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d5fc5-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d5fc5-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d5fc5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d5fc5-105">Zwraca liczbę całkowitą reprezentującą bity Z tablicy operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="d5fc5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d5fc5-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="d5fc5-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d5fc5-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d5fc5-108">Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="d5fc5-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5fc5-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5fc5-110">Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliX` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliY` lub `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="d5fc5-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5fc5-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d5fc5-111">Remarks</span></span>

<span data-ttu-id="d5fc5-112">Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5fc5-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d5fc5-113">See Also</span></span>

- [<span data-ttu-id="d5fc5-114">Microsoft. Quantum. bitowy. XBits</span><span class="sxs-lookup"><span data-stu-id="d5fc5-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)