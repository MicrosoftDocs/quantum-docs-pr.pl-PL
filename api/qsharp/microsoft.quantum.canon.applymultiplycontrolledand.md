---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717957"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="73892-102">ApplyMultiplyControlledAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="73892-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="73892-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73892-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73892-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73892-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73892-105">Implementuje bramę Toffoli o wielu kontrolowanej, przy założeniu, że docelowy qubit jest zainicjowany 0.</span><span class="sxs-lookup"><span data-stu-id="73892-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="73892-106">W przypadku operacji sąsiadujących zakłada się, że wartość docelowa qubit zostanie zresetowana do wartości 0.</span><span class="sxs-lookup"><span data-stu-id="73892-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="73892-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="73892-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="73892-108">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73892-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73892-109">Qubits kontrolki</span><span class="sxs-lookup"><span data-stu-id="73892-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="73892-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="73892-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="73892-111">Qubit docelowy</span><span class="sxs-lookup"><span data-stu-id="73892-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="73892-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73892-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

