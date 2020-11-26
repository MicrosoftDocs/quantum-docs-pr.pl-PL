---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218397"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="9080c-102">ApplyMultiplyControlledAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="9080c-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="9080c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9080c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9080c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9080c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9080c-105">Implementuje bramę Toffoli o wielu kontrolowanej, przy założeniu, że docelowy qubit jest zainicjowany 0.</span><span class="sxs-lookup"><span data-stu-id="9080c-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="9080c-106">W przypadku operacji sąsiadujących zakłada się, że wartość docelowa qubit zostanie zresetowana do wartości 0.</span><span class="sxs-lookup"><span data-stu-id="9080c-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9080c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9080c-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="9080c-108">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9080c-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9080c-109">Qubits kontrolki</span><span class="sxs-lookup"><span data-stu-id="9080c-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9080c-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9080c-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9080c-111">Qubit docelowy</span><span class="sxs-lookup"><span data-stu-id="9080c-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="9080c-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9080c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

