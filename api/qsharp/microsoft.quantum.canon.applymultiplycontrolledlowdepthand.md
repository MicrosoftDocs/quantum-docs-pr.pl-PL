---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841673"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="0aebf-102">ApplyMultiplyControlledLowDepthAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="0aebf-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="0aebf-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0aebf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0aebf-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0aebf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0aebf-105">Implementuje bramę Toffoli o wielu kontrolowanej, przy założeniu, że docelowy qubit jest zainicjowany 0.</span><span class="sxs-lookup"><span data-stu-id="0aebf-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="0aebf-106">W przypadku operacji sąsiadujących zakłada się, że wartość docelowa qubit zostanie zresetowana do wartości 0.</span><span class="sxs-lookup"><span data-stu-id="0aebf-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="0aebf-107">Wymaga głębokości Rz 1, podczas gdy liczba elementów pomocnik qubits jest wykładnicza w liczbie qubits.</span><span class="sxs-lookup"><span data-stu-id="0aebf-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0aebf-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0aebf-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="0aebf-109">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0aebf-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0aebf-110">Qubits kontrolki</span><span class="sxs-lookup"><span data-stu-id="0aebf-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0aebf-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0aebf-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0aebf-112">Qubit docelowy</span><span class="sxs-lookup"><span data-stu-id="0aebf-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="0aebf-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0aebf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

