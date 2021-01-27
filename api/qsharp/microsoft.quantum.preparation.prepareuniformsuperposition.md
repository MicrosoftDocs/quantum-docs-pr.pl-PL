---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854317"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="37378-102">PrepareUniformSuperposition, operacja</span><span class="sxs-lookup"><span data-stu-id="37378-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="37378-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="37378-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="37378-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37378-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37378-105">Tworzy jednolity nadpozycja w stosunku do Stanów, które kodują od 0 do `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="37378-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="37378-106">Oznacza to, że ta jednostka $U $ tworzy jednolity nadpozycja dla wszystkich stanów $0 $ do $M-$1, z uwzględnieniem stanu wejściowego $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="37378-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="37378-107">Innymi słowy, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="37378-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="37378-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="37378-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="37378-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="37378-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="37378-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37378-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37378-111">Wymagana liczba Stanów $M $ w jednolitej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="37378-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="37378-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="37378-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="37378-113">Rejestr qubit, który przechowuje liczbę stanów w `LittleEndian` formacie.</span><span class="sxs-lookup"><span data-stu-id="37378-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="37378-114">Ten rejestr musi być w stanie przechowywać liczbę $M-$1 i założono, że zostanie zainicjowany w stanie $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="37378-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37378-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37378-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="37378-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="37378-116">Example</span></span>

<span data-ttu-id="37378-117">Poniższy przykład przygotowuje stan $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ on $3 $ qubits.</span><span class="sxs-lookup"><span data-stu-id="37378-117">The following example prepares the state $\frac{1}{\sqrt{6}}\sum_{j=0}^{5}\ket{j}$ on $3$ qubits.</span></span>

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a><span data-ttu-id="37378-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37378-118">Remarks</span></span>

<span data-ttu-id="37378-119">Operacja jest Współrzędna, ale wymaga, aby `indexRegister` w tym przypadku w pierwszej kolejności były w jednolity sposób `nIndices` .</span><span class="sxs-lookup"><span data-stu-id="37378-119">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>