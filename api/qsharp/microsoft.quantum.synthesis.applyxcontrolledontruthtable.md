---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203301"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="f83e3-102">ApplyXControlledOnTruthTable, operacja</span><span class="sxs-lookup"><span data-stu-id="f83e3-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="f83e3-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f83e3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f83e3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f83e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f83e3-105">Stosuje @"microsoft.quantum.intrinsic.x" operację na `target` , jeśli funkcja logiczna `func` zwróci wartość true dla klasycznego przypisania w `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="f83e3-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f83e3-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f83e3-106">Description</span></span>

<span data-ttu-id="f83e3-107">Operacja implementuje operacje jednostkowe \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, gdzie $x $ i $y $ reprezentuje `controlRegister` odpowiednio i `target` .</span><span class="sxs-lookup"><span data-stu-id="f83e3-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="f83e3-108">Funkcja logiczna $f $ jest reprezentowana jako tabela prawdy w warunkach dużej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="f83e3-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="f83e3-109">Na przykład większość funkcji na trzech danych wejściowych jest reprezentowana przez bitstring `11101000` , gdzie najbardziej znaczący bit `1` odpowiada przypisaniu wejściowemu `(1, 1, 1)` , a najmniej znaczący bit `0` odpowiada przypisaniu wejściowemu `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="f83e3-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="f83e3-110">Może być reprezentowana przez dużą liczbę całkowitą `0xE8L` w notacji szesnastkowej lub jako `232L` notację dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="f83e3-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="f83e3-111">`L`Sufiks wskazuje, że stała jest typu `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="f83e3-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="f83e3-112">Więcej szczegółów na temat tej reprezentacji można znaleźć w [tabelach prawdy Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="f83e3-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="f83e3-113">Implementacja wykorzystuje @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" bramy i.</span><span class="sxs-lookup"><span data-stu-id="f83e3-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="f83e3-114">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f83e3-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="f83e3-115">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f83e3-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f83e3-116">Tabela wartości logicznych prawdy reprezentowana jako duża liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="f83e3-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="f83e3-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f83e3-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f83e3-118">Rejestr kontroli qubits</span><span class="sxs-lookup"><span data-stu-id="f83e3-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f83e3-119">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f83e3-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f83e3-120">Qubit docelowy</span><span class="sxs-lookup"><span data-stu-id="f83e3-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="f83e3-121">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f83e3-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f83e3-122">Odwołania</span><span class="sxs-lookup"><span data-stu-id="f83e3-122">References</span></span>

- [<span data-ttu-id="f83e3-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, ArXiv: Quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="f83e3-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="f83e3-124">*Mathias Soeken*, *Martin Roetteler*, ArXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="f83e3-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="f83e3-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f83e3-125">See Also</span></span>

- [<span data-ttu-id="f83e3-126">Microsoft. Quantum. synteza. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="f83e3-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)