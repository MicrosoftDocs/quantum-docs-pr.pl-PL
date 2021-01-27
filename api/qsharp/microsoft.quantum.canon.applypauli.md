---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844750"
---
# <a name="applypauli-operation"></a><span data-ttu-id="3df5a-102">ApplyPauli, operacja</span><span class="sxs-lookup"><span data-stu-id="3df5a-102">ApplyPauli operation</span></span>

<span data-ttu-id="3df5a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3df5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3df5a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3df5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3df5a-105">Za pomocą wieloqubitowego operatora Pauli stosuje odpowiednią operację do rejestru.</span><span class="sxs-lookup"><span data-stu-id="3df5a-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3df5a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3df5a-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="3df5a-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="3df5a-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="3df5a-108">Wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="3df5a-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3df5a-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3df5a-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3df5a-110">Zarejestruj się, aby zastosować daną operację Pauli na.</span><span class="sxs-lookup"><span data-stu-id="3df5a-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3df5a-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3df5a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="3df5a-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="3df5a-112">Example</span></span>

<span data-ttu-id="3df5a-113">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="3df5a-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="3df5a-114">oraz</span><span class="sxs-lookup"><span data-stu-id="3df5a-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```