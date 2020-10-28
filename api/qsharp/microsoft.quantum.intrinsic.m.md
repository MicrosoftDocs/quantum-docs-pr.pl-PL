---
uid: Microsoft.Quantum.Intrinsic.M
title: Operacja M
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720936"
---
# <a name="m-operation"></a><span data-ttu-id="dbccd-102">Operacja M</span><span class="sxs-lookup"><span data-stu-id="dbccd-102">M operation</span></span>

<span data-ttu-id="dbccd-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="dbccd-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="dbccd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbccd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbccd-105">Wykonuje pomiary jednego qubit w bazie Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="dbccd-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="dbccd-106">Wynik wyjściowy jest podawany przez dystrybucję \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="dbccd-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="dbccd-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="dbccd-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="dbccd-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dbccd-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="dbccd-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dbccd-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dbccd-110">Qubit.</span><span class="sxs-lookup"><span data-stu-id="dbccd-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dbccd-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="dbccd-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dbccd-112">`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="dbccd-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbccd-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dbccd-113">Remarks</span></span>

<span data-ttu-id="dbccd-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="dbccd-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```