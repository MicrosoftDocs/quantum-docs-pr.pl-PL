---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: PrepareChoiStateCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709445"
---
# <a name="preparechoistateca-operation"></a><span data-ttu-id="d4f06-102">PrepareChoiStateCA, operacja</span><span class="sxs-lookup"><span data-stu-id="d4f06-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="d4f06-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d4f06-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d4f06-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4f06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4f06-105">Przygotowuje stan Choi – Jamiłkowski dla danej operacji z wariantami kontrolowanymi i przylegającymi do określonych rejestrów referencyjnych i docelowych.</span><span class="sxs-lookup"><span data-stu-id="d4f06-105">Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d4f06-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d4f06-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="d4f06-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="d4f06-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="d4f06-108">odwołanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d4f06-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="d4f06-109">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d4f06-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="d4f06-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4f06-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d4f06-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d4f06-111">See Also</span></span>

- [<span data-ttu-id="d4f06-112">Microsoft. Quantum. przygotowaniu. PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="d4f06-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)