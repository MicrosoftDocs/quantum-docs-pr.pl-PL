---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: 7f42d9cab2f80f8f826ad1268b050134f0540cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218227"
---
# <a name="applypauli-operation"></a><span data-ttu-id="f2304-102">ApplyPauli, operacja</span><span class="sxs-lookup"><span data-stu-id="f2304-102">ApplyPauli operation</span></span>

<span data-ttu-id="f2304-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2304-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2304-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2304-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2304-105">Za pomocą wieloqubitowego operatora Pauli stosuje odpowiednią operację do rejestru.</span><span class="sxs-lookup"><span data-stu-id="f2304-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f2304-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f2304-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="f2304-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="f2304-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="f2304-108">Wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="f2304-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f2304-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2304-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2304-110">Zarejestruj się, aby zastosować daną operację Pauli na.</span><span class="sxs-lookup"><span data-stu-id="f2304-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2304-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2304-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

