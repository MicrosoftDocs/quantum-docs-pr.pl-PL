---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: Funkcja _PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710663"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="8bb40-102">Funkcja _PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="8bb40-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="8bb40-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8bb40-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8bb40-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bb40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bb40-105">Tworzy moduł kodowania bloku dla hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8bb40-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="8bb40-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ jest opisywany przez sumę Pauliych warunków $P _j $, każdy z rzeczywistym czynnikiem $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="8bb40-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="8bb40-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8bb40-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="8bb40-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8bb40-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="8bb40-109">A `GeneratorSystem` , który opisuje $H $ jako sumę Pauli warunków</span><span class="sxs-lookup"><span data-stu-id="8bb40-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="8bb40-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL</span><span class="sxs-lookup"><span data-stu-id="8bb40-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8bb40-111">Operacja jednostkowa $V $, która stosuje $V jednostkowe _j $ kontrolowane w indeksie $ \ket{j} $, przy użyciu funkcji $f: j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="8bb40-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="8bb40-112">multiplekser: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL</span><span class="sxs-lookup"><span data-stu-id="8bb40-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="8bb40-113">Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="8bb40-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="8bb40-114">Pierwszy parametr</span><span class="sxs-lookup"><span data-stu-id="8bb40-114">First parameter</span></span>

<span data-ttu-id="8bb40-115">Jedna z norm współczynników $ \Alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="8bb40-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="8bb40-116">Drugi parametr</span><span class="sxs-lookup"><span data-stu-id="8bb40-116">Second parameter</span></span>

<span data-ttu-id="8bb40-117">`BlockEncodingReflection`Jednostkowa $U $ Hamiltonian $U $.</span><span class="sxs-lookup"><span data-stu-id="8bb40-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="8bb40-118">Ponieważ ta jednostka jest taka sama jak $U ^ 2 = I $, jest również odbiciem.</span><span class="sxs-lookup"><span data-stu-id="8bb40-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bb40-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8bb40-119">Remarks</span></span>

<span data-ttu-id="8bb40-120">Przykładowe operacje przygotowywania i deprzygotowywania stanu $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ i konstruowania jednostek z kontrolą pomnożoną <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="8bb40-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>