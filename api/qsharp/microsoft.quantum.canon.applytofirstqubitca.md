---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717397"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="c86f8-102">ApplyToFirstQubitCA, operacja</span><span class="sxs-lookup"><span data-stu-id="c86f8-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="c86f8-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c86f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c86f8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c86f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c86f8-105">Stosuje operację do pierwszej qubit w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="c86f8-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="c86f8-106">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="c86f8-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c86f8-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c86f8-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="c86f8-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL</span><span class="sxs-lookup"><span data-stu-id="c86f8-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c86f8-109">Operacja, która ma zostać zastosowana do pierwszego qubit</span><span class="sxs-lookup"><span data-stu-id="c86f8-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c86f8-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c86f8-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c86f8-111">Qubit tablicę do pierwszej qubit, do której zostanie zastosowana operacja</span><span class="sxs-lookup"><span data-stu-id="c86f8-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c86f8-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c86f8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c86f8-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c86f8-113">See Also</span></span>

- [<span data-ttu-id="c86f8-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="c86f8-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)