---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222953"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="3c44c-102">IncrementByModularInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="3c44c-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="3c44c-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3c44c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3c44c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c44c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c44c-105">Wykonuje modularny przyrost qubit rejestru przez stałą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="3c44c-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3c44c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3c44c-106">Description</span></span>

<span data-ttu-id="3c44c-107">Poinformuj nas `increment` o $a $, `modulus` przez $N $ i Integer zakodowane w `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="3c44c-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="3c44c-108">Następnie operacja wykonuje następujące przekształcenia: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} INTEGERS są kodowane w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="3c44c-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="3c44c-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3c44c-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="3c44c-110">Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c44c-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c44c-111">Przyrost liczby całkowitej $a $, który ma zostać dodany do $y $.</span><span class="sxs-lookup"><span data-stu-id="3c44c-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="3c44c-112">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c44c-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c44c-113">Liczba całkowita $N $, która modyfikacje $y + a $.</span><span class="sxs-lookup"><span data-stu-id="3c44c-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="3c44c-114">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3c44c-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3c44c-115">Liczba całkowita $y $ w `LittleEndian` formacie, który `increment` $a $ jest dodawany do.</span><span class="sxs-lookup"><span data-stu-id="3c44c-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c44c-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c44c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c44c-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3c44c-117">Remarks</span></span>

<span data-ttu-id="3c44c-118">Przyjęto, że początkowa wartość docelowa jest mniejsza niż $N $ i że przyrost $a $ jest mniejszy niż $N $.</span><span class="sxs-lookup"><span data-stu-id="3c44c-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="3c44c-119">Należy pamiętać, że <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementuje tę samą operację na `PhaseLittleEndian` podstawie.</span><span class="sxs-lookup"><span data-stu-id="3c44c-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c44c-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3c44c-120">See Also</span></span>

- [<span data-ttu-id="3c44c-121">Microsoft. Quantum. arytmetyczne. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="3c44c-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)