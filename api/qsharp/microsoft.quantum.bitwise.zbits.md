---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842058"
---
# <a name="zbits-function"></a><span data-ttu-id="257cc-102">ZBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="257cc-102">ZBits function</span></span>

<span data-ttu-id="257cc-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="257cc-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="257cc-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="257cc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="257cc-105">Zwraca liczbę całkowitą reprezentującą bity Z tablicy operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="257cc-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="257cc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="257cc-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="257cc-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="257cc-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="257cc-108">Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="257cc-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="257cc-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="257cc-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="257cc-110">Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliX` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliY` lub `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="257cc-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="257cc-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="257cc-111">Remarks</span></span>

<span data-ttu-id="257cc-112">Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.</span><span class="sxs-lookup"><span data-stu-id="257cc-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="257cc-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="257cc-113">See Also</span></span>

- [<span data-ttu-id="257cc-114">Microsoft. Quantum. bitowy. XBits</span><span class="sxs-lookup"><span data-stu-id="257cc-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)