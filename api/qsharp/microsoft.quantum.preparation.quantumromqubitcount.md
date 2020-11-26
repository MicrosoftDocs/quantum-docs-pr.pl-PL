---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210407"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="49cf3-102">QuantumROMQubitCount, funkcja</span><span class="sxs-lookup"><span data-stu-id="49cf3-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="49cf3-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="49cf3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="49cf3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49cf3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="49cf3-105">QuantumROMQubitCount jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="49cf3-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="49cf3-106">Użyj <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="49cf3-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="49cf3-107">Zwraca łączną liczbę qubits, które muszą zostać przydzielone do operacji zwróconej przez `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="49cf3-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="49cf3-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="49cf3-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="49cf3-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="49cf3-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="49cf3-110">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="49cf3-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="49cf3-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49cf3-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49cf3-112">Liczba współczynników określonych w `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="49cf3-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="49cf3-113">Wynik: ([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="49cf3-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="49cf3-114">Pierwszy parametr</span><span class="sxs-lookup"><span data-stu-id="49cf3-114">First parameter</span></span>

<span data-ttu-id="49cf3-115">Krotka `(x,(y,z))` `x = y + z` , gdzie jest łączna liczba przydzieloną qubits, `y` jest liczbą qubits dla `LittleEndian` rejestru i `z` jest liczbą qubits elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="49cf3-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>