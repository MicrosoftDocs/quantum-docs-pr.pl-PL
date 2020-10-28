---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717817"
---
# <a name="applypauli-operation"></a><span data-ttu-id="c1d04-102">ApplyPauli, operacja</span><span class="sxs-lookup"><span data-stu-id="c1d04-102">ApplyPauli operation</span></span>

<span data-ttu-id="c1d04-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1d04-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1d04-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1d04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1d04-105">Za pomocą wieloqubitowego operatora Pauli stosuje odpowiednią operację do rejestru.</span><span class="sxs-lookup"><span data-stu-id="c1d04-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c1d04-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c1d04-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="c1d04-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c1d04-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c1d04-108">Wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="c1d04-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c1d04-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1d04-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1d04-110">Zarejestruj się, aby zastosować daną operację Pauli na.</span><span class="sxs-lookup"><span data-stu-id="c1d04-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1d04-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1d04-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

