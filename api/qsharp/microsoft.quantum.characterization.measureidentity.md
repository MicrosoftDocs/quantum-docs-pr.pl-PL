---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714966"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="b43ac-102">MeasureIdentity, operacja</span><span class="sxs-lookup"><span data-stu-id="b43ac-102">MeasureIdentity operation</span></span>

<span data-ttu-id="b43ac-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b43ac-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="b43ac-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b43ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b43ac-105">Mierzy operator tożsamości w rejestrze qubits.</span><span class="sxs-lookup"><span data-stu-id="b43ac-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="b43ac-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b43ac-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="b43ac-107">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b43ac-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b43ac-108">Rejestr, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="b43ac-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b43ac-109">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="b43ac-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="b43ac-110">Wartość wyniku `Zero` .</span><span class="sxs-lookup"><span data-stu-id="b43ac-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b43ac-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b43ac-111">Remarks</span></span>

<span data-ttu-id="b43ac-112">Ponieważ $ \boldone $ ma tylko eigenvalue $1 $ i nie ma negatywnej eigenvalue, ta operacja zawsze zwraca wartość `Zero` odpowiadającą eigenvalue $ + 1 = (-1) ^ 0 $ i nie powoduje zwinięcia stanu `register` .</span><span class="sxs-lookup"><span data-stu-id="b43ac-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="b43ac-113">Ta operacja nie jest przydatna, ale jest przydatna w kontekście Tomography procesu, ponieważ zawiera informacje na temat zachowywania śledzenia procesów Quantum.</span><span class="sxs-lookup"><span data-stu-id="b43ac-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="b43ac-114">W szczególności maszyna docelowa ze skalą stratną powinna zastąpić tę operację rzeczywistą wartością miary $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="b43ac-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>