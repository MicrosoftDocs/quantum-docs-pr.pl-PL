---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operacja miary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818764"
---
# <a name="measure-operation"></a><span data-ttu-id="5205c-102">Operacja miary</span><span class="sxs-lookup"><span data-stu-id="5205c-102">Measure operation</span></span>

<span data-ttu-id="5205c-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5205c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5205c-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5205c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5205c-105">Wykonuje wspólne pomiary co najmniej jednego qubits w określonych bazach Pauli.</span><span class="sxs-lookup"><span data-stu-id="5205c-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="5205c-106">Wynik danych wyjściowych jest podawany przez dystrybucję: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align}, gdzie $P _i $ to $i $ th elementu `bases` , i gdzie $N = \texttt{length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="5205c-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="5205c-107">Oznacza to, że pomiar zwraca `Result` $d $ w taki sposób, że eigenvalue zaobserwowanego efektu pomiarowego wynosi $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="5205c-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="5205c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5205c-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="5205c-109">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="5205c-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="5205c-110">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="5205c-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5205c-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5205c-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5205c-112">Rejestr qubits, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="5205c-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5205c-113">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="5205c-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5205c-114">`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="5205c-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5205c-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5205c-115">Remarks</span></span>

<span data-ttu-id="5205c-116">Jeśli tablica podstawa i tablica qubit są różne długości, operacja zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="5205c-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>