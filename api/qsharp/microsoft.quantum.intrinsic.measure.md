---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operacja miary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711452"
---
# <a name="measure-operation"></a><span data-ttu-id="29ce9-102">Operacja miary</span><span class="sxs-lookup"><span data-stu-id="29ce9-102">Measure operation</span></span>

<span data-ttu-id="29ce9-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="29ce9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="29ce9-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29ce9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29ce9-105">Wykonuje wspólne pomiary co najmniej jednego qubits w określonych bazach Pauli.</span><span class="sxs-lookup"><span data-stu-id="29ce9-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="29ce9-106">Wynik danych wyjściowych jest podawany przez dystrybucję: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align}, gdzie $P _i $ to $i $ th elementu `bases` , i gdzie $N = \texttt{length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="29ce9-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="29ce9-107">Oznacza to, że pomiar zwraca `Result` $d $ w taki sposób, że eigenvalue zaobserwowanego efektu pomiarowego wynosi $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="29ce9-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="29ce9-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="29ce9-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="29ce9-109">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="29ce9-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="29ce9-110">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="29ce9-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="29ce9-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="29ce9-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="29ce9-112">Rejestr qubits, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="29ce9-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="29ce9-113">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="29ce9-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="29ce9-114">`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="29ce9-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="29ce9-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="29ce9-115">Remarks</span></span>

<span data-ttu-id="29ce9-116">Jeśli tablica podstawa i tablica qubit są różne długości, operacja zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="29ce9-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>