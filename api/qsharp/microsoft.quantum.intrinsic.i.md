---
uid: Microsoft.Quantum.Intrinsic.I
title: Operacja I
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849405"
---
# <a name="i-operation"></a><span data-ttu-id="104e9-102">Operacja I</span><span class="sxs-lookup"><span data-stu-id="104e9-102">I operation</span></span>

<span data-ttu-id="104e9-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="104e9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="104e9-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="104e9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="104e9-105">Wykonuje operację Identity (No-op) w jednej qubit.</span><span class="sxs-lookup"><span data-stu-id="104e9-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="104e9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="104e9-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="104e9-107">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="104e9-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="104e9-108">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="104e9-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="104e9-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="104e9-109">Remarks</span></span>

<span data-ttu-id="104e9-110">To nie jest.</span><span class="sxs-lookup"><span data-stu-id="104e9-110">This is a no-op.</span></span> <span data-ttu-id="104e9-111">Jest ona dostępna do kompletności i ponieważ czasami warto wywołać tożsamość w algorytmie lub przekazać ją jako parametr.</span><span class="sxs-lookup"><span data-stu-id="104e9-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>