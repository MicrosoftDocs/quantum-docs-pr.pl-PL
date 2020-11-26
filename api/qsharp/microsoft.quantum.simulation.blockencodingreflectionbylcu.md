---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: e1247d961a7ebce798106c24c46d924dd6e6d347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229481"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="a58f3-102">BlockEncodingReflectionByLCU, funkcja</span><span class="sxs-lookup"><span data-stu-id="a58f3-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="a58f3-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a58f3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a58f3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a58f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a58f3-105">Koduje operatora zainteresowania `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="a58f3-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="a58f3-106">To konstruuje `BlockEncodingReflection` $U jednostkowe = P\cdot V\cdot P ^ \dagger $, który koduje niektóre operatory $H = \ sum_ {j} | \ alpha_j | U_j $ znaczenie, które jest liniową kombinacją unitaries.</span><span class="sxs-lookup"><span data-stu-id="a58f3-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="a58f3-107">Zwykle $P $ jest jednostką przygotowań stanu, taką jak $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, i $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="a58f3-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="a58f3-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a58f3-108">Input</span></span>

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a><span data-ttu-id="a58f3-109">statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="a58f3-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a58f3-110">Jednostkowy $P $, który przygotowuje jakiś stan docelowy.</span><span class="sxs-lookup"><span data-stu-id="a58f3-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="a58f3-111">Selektor: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="a58f3-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a58f3-112">Jednostkowy $V $, który koduje składnik unitaries $H $.</span><span class="sxs-lookup"><span data-stu-id="a58f3-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="a58f3-113">Wynik: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="a58f3-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="a58f3-114">Jednostkowe $U $ działające wspólnie z rejestrami `a` i `s` zakodowaniami bloków $H $ i spełniają $U "^ {-1} = U $.</span><span class="sxs-lookup"><span data-stu-id="a58f3-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="a58f3-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a58f3-115">Remarks</span></span>

<span data-ttu-id="a58f3-116">Ta `BlockEncoding` implementacja zapewnia właściwości `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="a58f3-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a58f3-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a58f3-117">See Also</span></span>

- [<span data-ttu-id="a58f3-118">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="a58f3-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="a58f3-119">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="a58f3-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)