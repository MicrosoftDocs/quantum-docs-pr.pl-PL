---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712586"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="627c3-102">GetQubitsAvailableToBorrow, operacja</span><span class="sxs-lookup"><span data-stu-id="627c3-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="627c3-103">Przestrzeń nazw: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="627c3-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="627c3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="627c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="627c3-105">Zwraca liczbę qubits, które są obecnie dostępne do zażyczania.</span><span class="sxs-lookup"><span data-stu-id="627c3-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="627c3-106">Obejmuje to nieużywane qubits; oznacza to, że obejmuje to qubits zwrócone przez `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="627c3-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="627c3-107">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="627c3-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="627c3-108">Liczba qubits, które mogą zostać przydzieloną w `borrowing` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="627c3-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="627c3-109">Jeśli używana maszyna docelowa nie dostarcza tych informacji, `-1` zostanie zwrócona wartość.</span><span class="sxs-lookup"><span data-stu-id="627c3-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="627c3-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="627c3-110">See Also</span></span>

- [<span data-ttu-id="627c3-111">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="627c3-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)