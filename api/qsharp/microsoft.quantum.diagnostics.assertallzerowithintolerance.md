---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713043"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="15a7c-102">AssertAllZeroWithinTolerance, operacja</span><span class="sxs-lookup"><span data-stu-id="15a7c-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="15a7c-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="15a7c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="15a7c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15a7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15a7c-105">Potwierdzenie, że podano qubits, są w {0} stanie $ \ket $ do danej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="15a7c-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="15a7c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="15a7c-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="15a7c-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="15a7c-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="15a7c-108">Qubits, które mają być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="15a7c-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="15a7c-109">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="15a7c-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="15a7c-110">Dokładność, w której stan powinien znajdować się w {0} stanie $ \ket $</span><span class="sxs-lookup"><span data-stu-id="15a7c-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="15a7c-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15a7c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="15a7c-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15a7c-112">See Also</span></span>

- [<span data-ttu-id="15a7c-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="15a7c-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)