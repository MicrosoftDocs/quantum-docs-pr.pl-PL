---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717402"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="b0462-102">ApplyToFirstQubitA, operacja</span><span class="sxs-lookup"><span data-stu-id="b0462-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="b0462-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0462-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0462-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0462-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0462-105">Stosuje operację do pierwszego qubit w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="b0462-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="b0462-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="b0462-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b0462-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b0462-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="b0462-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="b0462-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b0462-109">Operacja, która ma zostać zastosowana do pierwszego qubit</span><span class="sxs-lookup"><span data-stu-id="b0462-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b0462-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b0462-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b0462-111">Qubit tablicę do pierwszej qubit, do której zostanie zastosowana operacja</span><span class="sxs-lookup"><span data-stu-id="b0462-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0462-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0462-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b0462-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0462-113">See Also</span></span>

- [<span data-ttu-id="b0462-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="b0462-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)