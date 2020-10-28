---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721569"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="8091a-102">ApplyOuterCDKMAdder, operacja</span><span class="sxs-lookup"><span data-stu-id="8091a-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="8091a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8091a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8091a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8091a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8091a-105">Odwracalna, w miejscu — Przenieś operację, która jest używana w operacji dodawania liczby całkowitej RippleCarryAdderCDKM poniżej.</span><span class="sxs-lookup"><span data-stu-id="8091a-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="8091a-106">W przypadku dwóch rejestrów qubit `xs` i `ys` o tej samej długości operacja stosuje sekwencję CNOT i CCNOT bram z qubits w `xs` i `ys` jako `xs` elementy docelowe.</span><span class="sxs-lookup"><span data-stu-id="8091a-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8091a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8091a-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="8091a-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8091a-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8091a-109">Pierwszy rejestr qubit zawierający kontrolki i obiekty docelowe.</span><span class="sxs-lookup"><span data-stu-id="8091a-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="8091a-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8091a-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8091a-111">Drugi rejestr qubit, który przyczynia się do kontrolek.</span><span class="sxs-lookup"><span data-stu-id="8091a-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="8091a-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8091a-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8091a-113">Ancilla qubit używany w RippleCarryAdderCDKM przeszedł do tej operacji.</span><span class="sxs-lookup"><span data-stu-id="8091a-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8091a-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8091a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="8091a-115">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="8091a-115">References</span></span>

- <span data-ttu-id="8091a-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.</span><span class="sxs-lookup"><span data-stu-id="8091a-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1