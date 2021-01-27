---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 28a7c7877a3d48fd5ba50384d7996017e7cdb14f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837245"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="71f8b-102">OptimizedBEXY, operacja</span><span class="sxs-lookup"><span data-stu-id="71f8b-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="71f8b-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="71f8b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="71f8b-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="71f8b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="71f8b-105">Jednostkowa $U $, która stosuje ciąg Pauli w $ (X ^ {z + 1} z \_ PR ^ {z} \_ p) z \_ {p-1}... Z_0 $ qubits $0.. p $ Conditional na indeksie $z \In \{ 0, 1 \} $ i $p $.</span><span class="sxs-lookup"><span data-stu-id="71f8b-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="71f8b-106">Oznacza to, że $ $ \begin{align} U\ket {z} \ KET {p} \ KET {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} z \_ PR ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="71f8b-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="71f8b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="71f8b-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="71f8b-108">pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="71f8b-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="71f8b-109">Gdy qubit jest w stanie $ \ket {0} $, zostanie zastosowany $X $.</span><span class="sxs-lookup"><span data-stu-id="71f8b-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="71f8b-110">Gdy jest w stanie $ \ket {1} $, zostanie zastosowany $Y $.</span><span class="sxs-lookup"><span data-stu-id="71f8b-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="71f8b-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="71f8b-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="71f8b-112">Stan $ \ket{p} $ tej rejestracji określa qubit, na których zastosowano $X $ lub $Y $.</span><span class="sxs-lookup"><span data-stu-id="71f8b-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="71f8b-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71f8b-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71f8b-114">Rejestr elementu qubits, na którym są stosowane operatory Pauli.</span><span class="sxs-lookup"><span data-stu-id="71f8b-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71f8b-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71f8b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="71f8b-116">Odwołania</span><span class="sxs-lookup"><span data-stu-id="71f8b-116">References</span></span>

- <span data-ttu-id="71f8b-117">Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="71f8b-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>