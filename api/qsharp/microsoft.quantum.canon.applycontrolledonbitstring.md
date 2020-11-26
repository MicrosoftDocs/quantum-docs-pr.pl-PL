---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219077"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="d1bd7-102">ApplyControlledOnBitString, operacja</span><span class="sxs-lookup"><span data-stu-id="d1bd7-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="d1bd7-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1bd7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1bd7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1bd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1bd7-105">Stosuje operacje jednostkowe na rejestrze docelowym, kontrolowane na podstawie stanu określonego przez daną maskę bitową.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d1bd7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d1bd7-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="d1bd7-107">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d1bd7-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d1bd7-108">Ciąg bitowy, który kontroluje daną operację jednostkową na.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="d1bd7-109">Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="d1bd7-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d1bd7-110">Operacja jednostkowa do zastosowania w rejestrze docelowym.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="d1bd7-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d1bd7-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d1bd7-112">Rejestr Quantum kontrolujący aplikację `oracle` .</span><span class="sxs-lookup"><span data-stu-id="d1bd7-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="d1bd7-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="d1bd7-113">targetRegister : 'T</span></span>

<span data-ttu-id="d1bd7-114">Docelowy rejestr, który ma zostać przesłany `oracle` jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1bd7-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1bd7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1bd7-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d1bd7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1bd7-117">'C</span><span class="sxs-lookup"><span data-stu-id="d1bd7-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d1bd7-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d1bd7-118">Remarks</span></span>

<span data-ttu-id="d1bd7-119">Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="d1bd7-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="d1bd7-120">Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="d1bd7-121">Na przykład `bits = [0,1,0,0,1]` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="d1bd7-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>