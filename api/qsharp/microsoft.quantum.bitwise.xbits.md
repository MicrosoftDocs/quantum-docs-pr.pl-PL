---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718560"
---
# <a name="xbits-function"></a><span data-ttu-id="1ea77-102">XBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="1ea77-102">XBits function</span></span>

<span data-ttu-id="1ea77-103">Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1ea77-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1ea77-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ea77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ea77-105">Zwraca liczbę całkowitą reprezentującą X bity tablicy operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="1ea77-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="1ea77-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1ea77-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="1ea77-107">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1ea77-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1ea77-108">Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="1ea77-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="1ea77-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ea77-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ea77-110">Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliZ` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliX` lub `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="1ea77-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ea77-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1ea77-111">Remarks</span></span>

<span data-ttu-id="1ea77-112">Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.</span><span class="sxs-lookup"><span data-stu-id="1ea77-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ea77-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ea77-113">See Also</span></span>

- [<span data-ttu-id="1ea77-114">Microsoft. Quantum. bitowy. ZBits</span><span class="sxs-lookup"><span data-stu-id="1ea77-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)