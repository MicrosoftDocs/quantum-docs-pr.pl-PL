---
uid: Microsoft.Quantum.Canon.SwapReverseRegister
title: SwapReverseRegister, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: SwapReverseRegister
qsharp.summary: Uses SWAP gates to Reversed the order of the qubits in a register.
ms.openlocfilehash: ca553670719c7cfff84f2eedad8cbc16189e0e98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852072"
---
# <a name="swapreverseregister-operation"></a><span data-ttu-id="dfcb0-102">SwapReverseRegister, operacja</span><span class="sxs-lookup"><span data-stu-id="dfcb0-102">SwapReverseRegister operation</span></span>

<span data-ttu-id="dfcb0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dfcb0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dfcb0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfcb0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfcb0-105">Używa bram wymiany do odwrócenia kolejności qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="dfcb0-105">Uses SWAP gates to Reversed the order of the qubits in a register.</span></span>

```qsharp
operation SwapReverseRegister (register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dfcb0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dfcb0-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="dfcb0-107">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dfcb0-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dfcb0-108">Porządek qubits, który należy odwrócić przy użyciu bram wymiany</span><span class="sxs-lookup"><span data-stu-id="dfcb0-108">The qubits order of which should be reversed using SWAP gates</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfcb0-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfcb0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

