---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 970acfbc63bc95542827988c5c81387e8812f289
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717822"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="9a318-102">ApplyOpRepeatedlyOverCA, operacja</span><span class="sxs-lookup"><span data-stu-id="9a318-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="9a318-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a318-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a318-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a318-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a318-105">Stosuje tę samą wartość operacji w przypadku rejestru qubit wiele razy.</span><span class="sxs-lookup"><span data-stu-id="9a318-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9a318-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9a318-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="9a318-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="9a318-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9a318-108">Operacja do zastosowania wiele razy w rejestrze qubit</span><span class="sxs-lookup"><span data-stu-id="9a318-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="9a318-109">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="9a318-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="9a318-110">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="9a318-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="9a318-111">Każda tablica powinna zawierać listę liczby całkowite opisujących qubits, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="9a318-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="9a318-112">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a318-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9a318-113">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="9a318-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a318-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a318-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9a318-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a318-115">See Also</span></span>

- [<span data-ttu-id="9a318-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="9a318-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)