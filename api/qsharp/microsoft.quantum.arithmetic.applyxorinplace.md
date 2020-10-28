---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721392"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="50180-102">ApplyXorInPlace, operacja</span><span class="sxs-lookup"><span data-stu-id="50180-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="50180-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="50180-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="50180-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50180-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50180-105">Stosuje operacje bitowe-XOR między klasyczną liczbą całkowitą i liczbą całkowitą reprezentowaną przez rejestr qubits.</span><span class="sxs-lookup"><span data-stu-id="50180-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="50180-106">Opis</span><span class="sxs-lookup"><span data-stu-id="50180-106">Description</span></span>

<span data-ttu-id="50180-107">Stosuje `X` operacje do qubits w rejestrze little-endian w oparciu o 1 bity w postaci liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="50180-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="50180-108">Poinformuj nas o tym, `value` że i pozwól y być liczbą całkowitą bez znaku `target` , a następnie `InPlaceXorLE` wykonuje operację określoną przez następującą mapę: $ \ket{y}\rightarrow \ket{y\oplus a} $, gdzie $ \oplus $ jest operatorem wyłącznym or.</span><span class="sxs-lookup"><span data-stu-id="50180-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="50180-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="50180-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="50180-110">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50180-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50180-111">Liczba całkowita, która przyjmuje wartość nieujemną.</span><span class="sxs-lookup"><span data-stu-id="50180-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="50180-112">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="50180-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="50180-113">Rejestr Quantum używany do przechowywania `value` w kodowaniu little-endian.</span><span class="sxs-lookup"><span data-stu-id="50180-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50180-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50180-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

