---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841960"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="e74ba-102">ApplyCNOTChain, operacja</span><span class="sxs-lookup"><span data-stu-id="e74ba-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="e74ba-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e74ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e74ba-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e74ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e74ba-105">Oblicza parzystość rejestru qubits w miejscu.</span><span class="sxs-lookup"><span data-stu-id="e74ba-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e74ba-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e74ba-106">Description</span></span>

<span data-ttu-id="e74ba-107">Ta operacja przekształca stan danych wejściowych jako $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="e74ba-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="e74ba-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e74ba-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e74ba-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e74ba-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="e74ba-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e74ba-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e74ba-111">Tablica qubits, której parzystość ma zostać obliczona i zapisana.</span><span class="sxs-lookup"><span data-stu-id="e74ba-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e74ba-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e74ba-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

