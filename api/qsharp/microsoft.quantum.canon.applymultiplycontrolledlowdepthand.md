---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717948"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="b7f06-102">ApplyMultiplyControlledLowDepthAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="b7f06-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="b7f06-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7f06-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7f06-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7f06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7f06-105">Implementuje bramę Toffoli o wielu kontrolowanej, przy założeniu, że docelowy qubit jest zainicjowany 0.</span><span class="sxs-lookup"><span data-stu-id="b7f06-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="b7f06-106">W przypadku operacji sąsiadujących zakłada się, że wartość docelowa qubit zostanie zresetowana do wartości 0.</span><span class="sxs-lookup"><span data-stu-id="b7f06-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="b7f06-107">Wymaga głębokości Rz 1, podczas gdy liczba elementów pomocnik qubits jest wykładnicza w liczbie qubits.</span><span class="sxs-lookup"><span data-stu-id="b7f06-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b7f06-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b7f06-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="b7f06-109">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b7f06-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b7f06-110">Qubits kontrolki</span><span class="sxs-lookup"><span data-stu-id="b7f06-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b7f06-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b7f06-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b7f06-112">Qubit docelowy</span><span class="sxs-lookup"><span data-stu-id="b7f06-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7f06-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7f06-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

