---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: Funkcja _ComputeJordanWignerBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714700"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="f3ffa-102">Funkcja _ComputeJordanWignerBitString</span><span class="sxs-lookup"><span data-stu-id="f3ffa-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="f3ffa-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f3ffa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f3ffa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3ffa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3ffa-105">Oblicza składnik Z programu Jordanii — ciąg Wigner między indeksami Fermion w operatorze fermionic z parzystą liczbą operatorów tworzenia i Annihilation.</span><span class="sxs-lookup"><span data-stu-id="f3ffa-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="f3ffa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f3ffa-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="f3ffa-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3ffa-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3ffa-108">Liczba fermions w systemie.</span><span class="sxs-lookup"><span data-stu-id="f3ffa-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="f3ffa-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f3ffa-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f3ffa-110">indeksy operatora fermionic.</span><span class="sxs-lookup"><span data-stu-id="f3ffa-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f3ffa-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f3ffa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f3ffa-112">Bitstring `Bool[]` , `true` w którym `PauliZ` należy zastosować.</span><span class="sxs-lookup"><span data-stu-id="f3ffa-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>