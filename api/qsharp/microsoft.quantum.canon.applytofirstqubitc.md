---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717411"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="50b16-102">ApplyToFirstQubitC, operacja</span><span class="sxs-lookup"><span data-stu-id="50b16-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="50b16-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50b16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50b16-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50b16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50b16-105">Stosuje operację do pierwszej qubit w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="50b16-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="50b16-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="50b16-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="50b16-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="50b16-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="50b16-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="50b16-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="50b16-109">Operacja, która ma zostać zastosowana do pierwszego qubit</span><span class="sxs-lookup"><span data-stu-id="50b16-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="50b16-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="50b16-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="50b16-111">Qubit tablicę do pierwszej qubit, do której zostanie zastosowana operacja</span><span class="sxs-lookup"><span data-stu-id="50b16-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="50b16-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50b16-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="50b16-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="50b16-113">See Also</span></span>

- [<span data-ttu-id="50b16-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="50b16-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)