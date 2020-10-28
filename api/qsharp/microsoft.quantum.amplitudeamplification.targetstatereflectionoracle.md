---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721727"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="aba2f-102">TargetStateReflectionOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="aba2f-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="aba2f-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="aba2f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="aba2f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aba2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aba2f-105">Konstruuje `ReflectionOracle` Informacje o stanie docelowym jednoznacznie oznaczone przez flagę qubit.</span><span class="sxs-lookup"><span data-stu-id="aba2f-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="aba2f-106">Stan docelowy ma jeden qubit ustawiony na 1, a wszystkie pozostałe 0: $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="aba2f-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="aba2f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aba2f-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="aba2f-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aba2f-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aba2f-109">Indeks do flagi qubit $f $ z programu Oracle.</span><span class="sxs-lookup"><span data-stu-id="aba2f-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="aba2f-110">Wynik: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="aba2f-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="aba2f-111">`ReflectionOracle`Odzwierciedla informacje o stanie oznaczonym przez $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="aba2f-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="aba2f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aba2f-112">See Also</span></span>

- [<span data-ttu-id="aba2f-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="aba2f-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)