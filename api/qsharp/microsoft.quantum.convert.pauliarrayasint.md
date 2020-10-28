---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713370"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="ae10b-102">PauliArrayAsInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="ae10b-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="ae10b-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ae10b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ae10b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae10b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae10b-105">Koduje wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli w postaci liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="ae10b-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="ae10b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ae10b-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="ae10b-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ae10b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ae10b-108">Tablica z co najwyżej 31 operatorami jednoqubitowych Pauli.</span><span class="sxs-lookup"><span data-stu-id="ae10b-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="ae10b-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae10b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae10b-110">Unikatowa identyfikacja liczby całkowitej `paulis` , zgodnie z poniższym opisem.</span><span class="sxs-lookup"><span data-stu-id="ae10b-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae10b-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ae10b-111">Remarks</span></span>

<span data-ttu-id="ae10b-112">Każdy operator Pauli można zakodować przy użyciu dwóch bitów: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="ae10b-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="ae10b-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ae10b-113">\end{align} $$</span></span>

<span data-ttu-id="ae10b-114">Dana tablica operatorów Pauli `[P0, ..., Pn]` , ta funkcja zwraca liczbę całkowitą z rozszerzeniem binarnym, łącząc mapowania każdego operatora Pauli w kolejności big-endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="ae10b-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>