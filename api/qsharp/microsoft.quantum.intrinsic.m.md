---
uid: Microsoft.Quantum.Intrinsic.M
title: Operacja M
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212345"
---
# <a name="m-operation"></a><span data-ttu-id="12b50-102">Operacja M</span><span class="sxs-lookup"><span data-stu-id="12b50-102">M operation</span></span>

<span data-ttu-id="12b50-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="12b50-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="12b50-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="12b50-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="12b50-105">Wykonuje pomiary jednego qubit w bazie Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="12b50-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="12b50-106">Wynik wyjściowy jest podawany przez dystrybucję \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="12b50-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="12b50-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="12b50-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="12b50-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="12b50-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="12b50-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="12b50-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="12b50-110">Qubit.</span><span class="sxs-lookup"><span data-stu-id="12b50-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="12b50-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="12b50-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="12b50-112">`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="12b50-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="12b50-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="12b50-113">Remarks</span></span>

<span data-ttu-id="12b50-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="12b50-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```