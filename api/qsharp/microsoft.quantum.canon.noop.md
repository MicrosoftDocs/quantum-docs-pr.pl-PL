---
uid: Microsoft.Quantum.Canon.NoOp
title: Aktualizujący nie działa, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852392"
---
# <a name="noop-operation"></a><span data-ttu-id="41d25-102">Aktualizujący nie działa, operacja</span><span class="sxs-lookup"><span data-stu-id="41d25-102">NoOp operation</span></span>

<span data-ttu-id="41d25-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41d25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41d25-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="41d25-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="41d25-105">Wykonuje operację Identity (No-op) w argumencie.</span><span class="sxs-lookup"><span data-stu-id="41d25-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="41d25-106">Opis</span><span class="sxs-lookup"><span data-stu-id="41d25-106">Description</span></span>

<span data-ttu-id="41d25-107">Ta operacja przyjmuje wartość dowolnego typu i nic nie robi.</span><span class="sxs-lookup"><span data-stu-id="41d25-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="41d25-108">Może to być przydatne, gdy oczekiwano danych wejściowych typu operacji, ale nie powinno być podejmowane żadne działanie.</span><span class="sxs-lookup"><span data-stu-id="41d25-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="41d25-109">Na przykład jeśli określony Syndrome korekcji błędów wskazuje, że nie wystąpił błąd, `NoOp<Qubit[]>` może to być poprawna procedura odzyskiwania.</span><span class="sxs-lookup"><span data-stu-id="41d25-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="41d25-110">Podobnie, jeśli operacja oczekuje procedury przygotowania stanu jako dane wejściowe, może służyć `NoOp<Qubit[]>` do przygotowania stanu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="41d25-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="41d25-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="41d25-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="41d25-112">dane wejściowe: t</span><span class="sxs-lookup"><span data-stu-id="41d25-112">input : 'T</span></span>

<span data-ttu-id="41d25-113">Wartość do zignorowania.</span><span class="sxs-lookup"><span data-stu-id="41d25-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41d25-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41d25-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41d25-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="41d25-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41d25-116">'C</span><span class="sxs-lookup"><span data-stu-id="41d25-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="41d25-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="41d25-117">Remarks</span></span>

<span data-ttu-id="41d25-118">We wszystkich przypadkach należy jawnie określić parametr typu dla `NoOp` .</span><span class="sxs-lookup"><span data-stu-id="41d25-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="41d25-119">Na przykład `NoOp<Qubit>` jest taka sama jak <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="41d25-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="41d25-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="41d25-120">See Also</span></span>

- [<span data-ttu-id="41d25-121">Microsoft. Quantum. wewnętrzna. I</span><span class="sxs-lookup"><span data-stu-id="41d25-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)