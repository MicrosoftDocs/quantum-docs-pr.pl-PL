---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718356"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="a5d14-102">ApplyControlledOnBitString, operacja</span><span class="sxs-lookup"><span data-stu-id="a5d14-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="a5d14-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5d14-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5d14-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5d14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5d14-105">Stosuje operacje jednostkowe na rejestrze docelowym, kontrolowane na podstawie stanu określonego przez daną maskę bitową.</span><span class="sxs-lookup"><span data-stu-id="a5d14-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="a5d14-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a5d14-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="a5d14-107">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a5d14-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a5d14-108">Ciąg bitowy, który kontroluje daną operację jednostkową na.</span><span class="sxs-lookup"><span data-stu-id="a5d14-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="a5d14-109">Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="a5d14-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a5d14-110">Operacja jednostkowa do zastosowania w rejestrze docelowym.</span><span class="sxs-lookup"><span data-stu-id="a5d14-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="a5d14-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5d14-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5d14-112">Rejestr Quantum kontrolujący aplikację `oracle` .</span><span class="sxs-lookup"><span data-stu-id="a5d14-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="a5d14-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="a5d14-113">targetRegister : 'T</span></span>

<span data-ttu-id="a5d14-114">Docelowy rejestr, który ma zostać przesłany `oracle` jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="a5d14-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5d14-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5d14-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a5d14-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a5d14-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5d14-117">'C</span><span class="sxs-lookup"><span data-stu-id="a5d14-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a5d14-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a5d14-118">Remarks</span></span>

<span data-ttu-id="a5d14-119">Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="a5d14-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="a5d14-120">Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="a5d14-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="a5d14-121">Na przykład `bits = [0,1,0,0,1]` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="a5d14-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>