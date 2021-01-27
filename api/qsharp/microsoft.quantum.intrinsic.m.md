---
uid: Microsoft.Quantum.Intrinsic.M
title: Operacja M
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818871"
---
# <a name="m-operation"></a><span data-ttu-id="dff95-102">Operacja M</span><span class="sxs-lookup"><span data-stu-id="dff95-102">M operation</span></span>

<span data-ttu-id="dff95-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="dff95-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="dff95-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dff95-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dff95-105">Wykonuje pomiary jednego qubit w bazie Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="dff95-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="dff95-106">Wynik wyjściowy jest podawany przez dystrybucję \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="dff95-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="dff95-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="dff95-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="dff95-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dff95-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="dff95-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dff95-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dff95-110">Qubit.</span><span class="sxs-lookup"><span data-stu-id="dff95-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dff95-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="dff95-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dff95-112">`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="dff95-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="dff95-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dff95-113">Remarks</span></span>

<span data-ttu-id="dff95-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="dff95-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```