---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: ef92e517ae40e76c94aff1121c78ece9985109fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857715"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="4869a-102">BlockEncodingReflectionByLCU, funkcja</span><span class="sxs-lookup"><span data-stu-id="4869a-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="4869a-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4869a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4869a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4869a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4869a-105">Koduje operatora zainteresowania `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="4869a-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="4869a-106">To konstruuje `BlockEncodingReflection` $U jednostkowe = P\cdot V\cdot P ^ \dagger $, który koduje niektóre operatory $H = \ sum_ {j} | \ alpha_j | U_j $ znaczenie, które jest liniową kombinacją unitaries.</span><span class="sxs-lookup"><span data-stu-id="4869a-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="4869a-107">Zwykle $P $ jest jednostką przygotowań stanu, taką jak $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, i $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="4869a-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="4869a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4869a-108">Input</span></span>

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a><span data-ttu-id="4869a-109">statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="4869a-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4869a-110">Jednostkowy $P $, który przygotowuje jakiś stan docelowy.</span><span class="sxs-lookup"><span data-stu-id="4869a-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="4869a-111">Selektor: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="4869a-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4869a-112">Jednostkowy $V $, który koduje składnik unitaries $H $.</span><span class="sxs-lookup"><span data-stu-id="4869a-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="4869a-113">Wynik: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="4869a-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="4869a-114">Jednostkowe $U $ działające wspólnie z rejestrami `a` i `s` zakodowaniami bloków $H $ i spełniają $U "^ {-1} = U $.</span><span class="sxs-lookup"><span data-stu-id="4869a-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="4869a-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4869a-115">Remarks</span></span>

<span data-ttu-id="4869a-116">Ta `BlockEncoding` implementacja zapewnia właściwości `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="4869a-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4869a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4869a-117">See Also</span></span>

- [<span data-ttu-id="4869a-118">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="4869a-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="4869a-119">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="4869a-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)