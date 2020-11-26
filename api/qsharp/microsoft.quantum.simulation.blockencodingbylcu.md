---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229549"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="2e2a7-102">BlockEncodingByLCU, funkcja</span><span class="sxs-lookup"><span data-stu-id="2e2a7-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="2e2a7-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2e2a7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2e2a7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e2a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e2a7-105">Koduje operatora zainteresowania `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="2e2a7-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="2e2a7-106">To konstruuje `BlockEncoding` $U jednostkowe = P\cdot V\cdot P ^ \dagger $, który koduje niektóre operatory $H = \ sum_ {j} | \ alpha_j | U_j $ znaczenie, które jest liniową kombinacją unitaries.</span><span class="sxs-lookup"><span data-stu-id="2e2a7-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="2e2a7-107">Zwykle $P $ jest jednostką przygotowań stanu, taką jak $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, i $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="2e2a7-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2e2a7-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2e2a7-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="2e2a7-109">statePreparation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="2e2a7-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2e2a7-110">Jednostkowy $P $, który przygotowuje jakiś stan docelowy.</span><span class="sxs-lookup"><span data-stu-id="2e2a7-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="2e2a7-111">Selektor: ('T,) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="2e2a7-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2e2a7-112">Jednostkowy $V $, który koduje składnik unitaries $H $.</span><span class="sxs-lookup"><span data-stu-id="2e2a7-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="2e2a7-113">Wynik: (t,) = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="2e2a7-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2e2a7-114">Jednostkowe $U $ działające wspólnie z rejestrami `a` i tymi `s` , które zablokują $H $, i spełniają $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="2e2a7-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e2a7-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2e2a7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e2a7-116">'C</span><span class="sxs-lookup"><span data-stu-id="2e2a7-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="2e2a7-117">Przeglądarki</span><span class="sxs-lookup"><span data-stu-id="2e2a7-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="2e2a7-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2e2a7-118">Remarks</span></span>

<span data-ttu-id="2e2a7-119">Ta `BlockEncoding` implementacja zapewnia właściwości `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="2e2a7-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e2a7-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e2a7-120">See Also</span></span>

- [<span data-ttu-id="2e2a7-121">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="2e2a7-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="2e2a7-122">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="2e2a7-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)