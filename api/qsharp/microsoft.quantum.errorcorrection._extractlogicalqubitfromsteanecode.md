---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operacja _ExtractLogicalQubitFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712558"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="dbd31-102">Operacja _ExtractLogicalQubitFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="dbd31-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="dbd31-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dbd31-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dbd31-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbd31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbd31-105">Syndrome pomiar i odwrotność osadzania.</span><span class="sxs-lookup"><span data-stu-id="dbd31-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="dbd31-106">$X $-i $Z $-stabilizatory nie są traktowane równo, co jest spowodowane szczególnym wyborem obwodu kodowania.</span><span class="sxs-lookup"><span data-stu-id="dbd31-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="dbd31-107">Ten element asymetrii prowadzi do innej procedury wyodrębniania Syndrome.</span><span class="sxs-lookup"><span data-stu-id="dbd31-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="dbd31-108">Jeden z nich może mierzyć Syndrome przez zmierzenie operatora Pauli qubit bezpośrednio w stanie kodu, ale w celu przeprowadzenia operacji logiczne qubit jest zwracany do jednego qubit, w wyniku którego można wykonać pomiary Syndrome bez dalszych ancillas.</span><span class="sxs-lookup"><span data-stu-id="dbd31-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="dbd31-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dbd31-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="dbd31-110">kod: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="dbd31-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="dbd31-111">Wynik: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="dbd31-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="dbd31-112">Logiczne qubit i para liczb całkowitych dla $X $-Syndrome i $Z $-Syndrome.</span><span class="sxs-lookup"><span data-stu-id="dbd31-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="dbd31-113">Reprezentują one indeks kodu qubit, w którym jeden $X $-lub $Z $-Error spowodował przemierzoną Syndrome.</span><span class="sxs-lookup"><span data-stu-id="dbd31-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbd31-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dbd31-114">Remarks</span></span>

<span data-ttu-id="dbd31-115">Należy zauważyć, że ta operacja nie jest oznaczona jako `internal` , ponieważ testy jednostkowe bezpośrednio zależą od tej operacji.</span><span class="sxs-lookup"><span data-stu-id="dbd31-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="dbd31-116">W przyszłości podczas przyszłego ulepszania testy jednostkowe powinny być refaktoryzacjne, aby zależały tylko od publicznie wywoływanych operacji.</span><span class="sxs-lookup"><span data-stu-id="dbd31-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="dbd31-117">Ta procedura jest dostosowana do określonego obwodu kodowania dla kodu qubit Steane. w przypadku zmodyfikowania obwodu kodowania wynik Syndrome może być interpretowany inaczej.</span><span class="sxs-lookup"><span data-stu-id="dbd31-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>