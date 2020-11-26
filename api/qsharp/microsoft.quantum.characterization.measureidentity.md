---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216119"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="6fca7-102">MeasureIdentity, operacja</span><span class="sxs-lookup"><span data-stu-id="6fca7-102">MeasureIdentity operation</span></span>

<span data-ttu-id="6fca7-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="6fca7-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="6fca7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fca7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fca7-105">Mierzy operator tożsamości w rejestrze qubits.</span><span class="sxs-lookup"><span data-stu-id="6fca7-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="6fca7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6fca7-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="6fca7-107">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6fca7-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6fca7-108">Rejestr, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="6fca7-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6fca7-109">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="6fca7-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6fca7-110">Wartość wyniku `Zero` .</span><span class="sxs-lookup"><span data-stu-id="6fca7-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fca7-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6fca7-111">Remarks</span></span>

<span data-ttu-id="6fca7-112">Ponieważ $ \boldone $ ma tylko eigenvalue $1 $ i nie ma negatywnej eigenvalue, ta operacja zawsze zwraca wartość `Zero` odpowiadającą eigenvalue $ + 1 = (-1) ^ 0 $ i nie powoduje zwinięcia stanu `register` .</span><span class="sxs-lookup"><span data-stu-id="6fca7-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="6fca7-113">Ta operacja nie jest przydatna, ale jest przydatna w kontekście Tomography procesu, ponieważ zawiera informacje na temat zachowywania śledzenia procesów Quantum.</span><span class="sxs-lookup"><span data-stu-id="6fca7-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="6fca7-114">W szczególności maszyna docelowa ze skalą stratną powinna zastąpić tę operację rzeczywistą wartością miary $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="6fca7-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>