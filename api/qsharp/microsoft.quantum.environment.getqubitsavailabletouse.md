---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712581"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="ea588-102">GetQubitsAvailableToUse, operacja</span><span class="sxs-lookup"><span data-stu-id="ea588-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="ea588-103">Przestrzeń nazw: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="ea588-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="ea588-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea588-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea588-105">Zwraca liczbę qubits, która jest obecnie dostępna do użycia.</span><span class="sxs-lookup"><span data-stu-id="ea588-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="ea588-106">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea588-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea588-107">Liczba qubits, które mogą zostać przydzieloną w `using` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ea588-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="ea588-108">Jeśli używana maszyna docelowa nie dostarcza tych informacji, `-1` zostanie zwrócona wartość.</span><span class="sxs-lookup"><span data-stu-id="ea588-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea588-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ea588-109">See Also</span></span>

- [<span data-ttu-id="ea588-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="ea588-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)