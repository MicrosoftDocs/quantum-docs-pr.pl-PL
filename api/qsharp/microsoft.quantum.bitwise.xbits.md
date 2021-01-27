---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845244"
---
# <a name="xbits-function"></a><span data-ttu-id="9ad54-102">XBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="9ad54-102">XBits function</span></span>

<span data-ttu-id="9ad54-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="9ad54-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="9ad54-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9ad54-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9ad54-105">Zwraca liczbę całkowitą reprezentującą X bity tablicy operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="9ad54-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="9ad54-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9ad54-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="9ad54-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9ad54-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9ad54-108">Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="9ad54-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="9ad54-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ad54-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ad54-110">Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliZ` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliX` lub `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="9ad54-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ad54-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9ad54-111">Remarks</span></span>

<span data-ttu-id="9ad54-112">Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.</span><span class="sxs-lookup"><span data-stu-id="9ad54-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad54-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9ad54-113">See Also</span></span>

- [<span data-ttu-id="9ad54-114">Microsoft. Quantum. bitowy. ZBits</span><span class="sxs-lookup"><span data-stu-id="9ad54-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)