---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: ApplyOpRepeatedlyOverC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717831"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="2b8a5-102">ApplyOpRepeatedlyOverC, operacja</span><span class="sxs-lookup"><span data-stu-id="2b8a5-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="2b8a5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b8a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b8a5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b8a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b8a5-105">Stosuje tę samą wartość operacji w przypadku rejestru qubit wiele razy.</span><span class="sxs-lookup"><span data-stu-id="2b8a5-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2b8a5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2b8a5-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="2b8a5-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="2b8a5-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="2b8a5-108">Operacja do zastosowania wiele razy w rejestrze qubit</span><span class="sxs-lookup"><span data-stu-id="2b8a5-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="2b8a5-109">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="2b8a5-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="2b8a5-110">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="2b8a5-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="2b8a5-111">Każda tablica powinna zawierać listę liczby całkowite opisujących qubits, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="2b8a5-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="2b8a5-112">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b8a5-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b8a5-113">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="2b8a5-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b8a5-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b8a5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2b8a5-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2b8a5-115">See Also</span></span>

- [<span data-ttu-id="2b8a5-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="2b8a5-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)