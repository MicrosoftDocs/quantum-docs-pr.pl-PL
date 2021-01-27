---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: Funkcja _ComputeJordanWignerBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839531"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="536ea-102">Funkcja _ComputeJordanWignerBitString</span><span class="sxs-lookup"><span data-stu-id="536ea-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="536ea-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="536ea-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="536ea-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="536ea-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="536ea-105">Oblicza składnik Z programu Jordanii — ciąg Wigner między indeksami Fermion w operatorze fermionic z parzystą liczbą operatorów tworzenia i Annihilation.</span><span class="sxs-lookup"><span data-stu-id="536ea-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="536ea-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="536ea-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="536ea-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="536ea-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="536ea-108">Liczba fermions w systemie.</span><span class="sxs-lookup"><span data-stu-id="536ea-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="536ea-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="536ea-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="536ea-110">indeksy operatora fermionic.</span><span class="sxs-lookup"><span data-stu-id="536ea-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="536ea-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="536ea-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="536ea-112">Bitstring `Bool[]` , `true` w którym `PauliZ` należy zastosować.</span><span class="sxs-lookup"><span data-stu-id="536ea-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="536ea-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="536ea-113">Example</span></span>

<span data-ttu-id="536ea-114">Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString to [false, false, false, true, true, true, false].</span><span class="sxs-lookup"><span data-stu-id="536ea-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>