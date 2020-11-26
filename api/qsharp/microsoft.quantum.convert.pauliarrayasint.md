---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224245"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="23d23-102">PauliArrayAsInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="23d23-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="23d23-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="23d23-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="23d23-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="23d23-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="23d23-105">Koduje wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli w postaci liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="23d23-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="23d23-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="23d23-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="23d23-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="23d23-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="23d23-108">Tablica z co najwyżej 31 operatorami jednoqubitowych Pauli.</span><span class="sxs-lookup"><span data-stu-id="23d23-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="23d23-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="23d23-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="23d23-110">Unikatowa identyfikacja liczby całkowitej `paulis` , zgodnie z poniższym opisem.</span><span class="sxs-lookup"><span data-stu-id="23d23-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="23d23-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="23d23-111">Remarks</span></span>

<span data-ttu-id="23d23-112">Każdy operator Pauli można zakodować przy użyciu dwóch bitów: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="23d23-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="23d23-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="23d23-113">\end{align} $$</span></span>

<span data-ttu-id="23d23-114">Dana tablica operatorów Pauli `[P0, ..., Pn]` , ta funkcja zwraca liczbę całkowitą z rozszerzeniem binarnym, łącząc mapowania każdego operatora Pauli w kolejności big-endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="23d23-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>