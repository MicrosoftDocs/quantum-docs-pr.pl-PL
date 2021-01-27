---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832710"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="a69d9-102">PauliArrayAsInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="a69d9-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="a69d9-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a69d9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a69d9-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a69d9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a69d9-105">Koduje wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli w postaci liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="a69d9-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="a69d9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a69d9-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="a69d9-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a69d9-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a69d9-108">Tablica z co najwyżej 31 operatorami jednoqubitowych Pauli.</span><span class="sxs-lookup"><span data-stu-id="a69d9-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="a69d9-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a69d9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a69d9-110">Unikatowa identyfikacja liczby całkowitej `paulis` , zgodnie z poniższym opisem.</span><span class="sxs-lookup"><span data-stu-id="a69d9-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="a69d9-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a69d9-111">Remarks</span></span>

<span data-ttu-id="a69d9-112">Każdy operator Pauli można zakodować przy użyciu dwóch bitów: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="a69d9-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="a69d9-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a69d9-113">\end{align} $$</span></span>

<span data-ttu-id="a69d9-114">Dana tablica operatorów Pauli `[P0, ..., Pn]` , ta funkcja zwraca liczbę całkowitą z rozszerzeniem binarnym, łącząc mapowania każdego operatora Pauli w kolejności big-endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="a69d9-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>