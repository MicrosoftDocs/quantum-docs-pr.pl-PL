---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724000"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="3d4f4-102">PrepareChoiState, operacja</span><span class="sxs-lookup"><span data-stu-id="3d4f4-102">PrepareChoiState operation</span></span>

<span data-ttu-id="3d4f4-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3d4f4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3d4f4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d4f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d4f4-105">Przygotowuje stan Choi – Jamiłkowski dla danej operacji do rejestrów referencyjnych i docelowych.</span><span class="sxs-lookup"><span data-stu-id="3d4f4-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3d4f4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3d4f4-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="3d4f4-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3d4f4-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3d4f4-108">Operacja $ \Lambda $, której stan Choi – Jamiłkowski $J (\Lambda)/2 ^ N $, ma zostać przygotowana, gdzie $N $ jest liczbą qubits, na których `op` działa.</span><span class="sxs-lookup"><span data-stu-id="3d4f4-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="3d4f4-109">odwołanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d4f4-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3d4f4-110">Rejestr qubits rozpoczynający się w stanie $ \ket{00\cdots 0} $, który ma być używany jako odwołanie do akcji `op` .</span><span class="sxs-lookup"><span data-stu-id="3d4f4-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3d4f4-111">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d4f4-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3d4f4-112">Rejestr qubits początkowo w stanie $ \ket{00\cdots 0} $, na którym `op` ma zostać zastosowany.</span><span class="sxs-lookup"><span data-stu-id="3d4f4-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d4f4-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d4f4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3d4f4-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3d4f4-114">Remarks</span></span>

<span data-ttu-id="3d4f4-115">Choi – Jamiłkowski State $J (\Lambda) $ procesu Quantum jest zdefiniowany jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ to *wektoryzacji* macierzy $X $ w Konwencji stosu kolumn.</span><span class="sxs-lookup"><span data-stu-id="3d4f4-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="3d4f4-116">Aby poznać klasyczny opis tego stanu, można uzyskać pełne informacje na temat efektu $ \Lambda $ działającego na dowolnych Stanach danych wejściowych i podstawą fundamentów *procesów Quantum Tomography* .</span><span class="sxs-lookup"><span data-stu-id="3d4f4-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="3d4f4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3d4f4-117">See Also</span></span>

- [<span data-ttu-id="3d4f4-118">Microsoft. Quantum. przygotowaniu. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="3d4f4-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="3d4f4-119">Microsoft. Quantum. przygotowaniu. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="3d4f4-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="3d4f4-120">Microsoft. Quantum. przygotowaniu. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="3d4f4-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)