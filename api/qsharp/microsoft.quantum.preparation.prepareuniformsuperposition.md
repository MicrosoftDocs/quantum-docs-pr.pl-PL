---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230093"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="76d27-102">PrepareUniformSuperposition, operacja</span><span class="sxs-lookup"><span data-stu-id="76d27-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="76d27-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="76d27-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="76d27-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76d27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76d27-105">Tworzy jednolity nadpozycja w stosunku do Stanów, które kodują od 0 do `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="76d27-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="76d27-106">Oznacza to, że ta jednostka $U $ tworzy jednolity nadpozycja dla wszystkich stanów $0 $ do $M-$1, z uwzględnieniem stanu wejściowego $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="76d27-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="76d27-107">Innymi słowy, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="76d27-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="76d27-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="76d27-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76d27-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="76d27-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="76d27-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76d27-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76d27-111">Wymagana liczba Stanów $M $ w jednolitej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="76d27-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="76d27-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="76d27-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="76d27-113">Rejestr qubit, który przechowuje liczbę stanów w `LittleEndian` formacie.</span><span class="sxs-lookup"><span data-stu-id="76d27-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="76d27-114">Ten rejestr musi być w stanie przechowywać liczbę $M-$1 i założono, że zostanie zainicjowany w stanie $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="76d27-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76d27-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76d27-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76d27-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="76d27-116">Remarks</span></span>

<span data-ttu-id="76d27-117">Operacja jest Współrzędna, ale wymaga, aby `indexRegister` w tym przypadku w pierwszej kolejności były w jednolity sposób `nIndices` .</span><span class="sxs-lookup"><span data-stu-id="76d27-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>