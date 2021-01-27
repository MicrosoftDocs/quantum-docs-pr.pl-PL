---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 2f96c2a8ed31d295bc127c568e0ca24c267638b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841450"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="245eb-102">ApplyToFirstQubitA, operacja</span><span class="sxs-lookup"><span data-stu-id="245eb-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="245eb-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="245eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="245eb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="245eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="245eb-105">Stosuje operację do pierwszego qubit w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="245eb-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="245eb-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="245eb-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="245eb-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="245eb-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="245eb-108">op: [](xref:microsoft.quantum.lang-ref.qubit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) qubit jest korektą</span><span class="sxs-lookup"><span data-stu-id="245eb-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="245eb-109">Operacja, która ma zostać zastosowana do pierwszego qubit</span><span class="sxs-lookup"><span data-stu-id="245eb-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="245eb-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="245eb-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="245eb-111">Qubit tablicę do pierwszej qubit, do której zostanie zastosowana operacja</span><span class="sxs-lookup"><span data-stu-id="245eb-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="245eb-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="245eb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="245eb-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="245eb-113">See Also</span></span>

- [<span data-ttu-id="245eb-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="245eb-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)