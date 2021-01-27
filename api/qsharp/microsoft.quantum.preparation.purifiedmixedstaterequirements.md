---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856832"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="80755-102">PurifiedMixedStateRequirements, funkcja</span><span class="sxs-lookup"><span data-stu-id="80755-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="80755-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="80755-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="80755-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80755-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80755-105">Zwraca łączną liczbę qubits, które muszą zostać przydzielone w celu zastosowania operacji zwróconej przez @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="80755-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="80755-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="80755-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="80755-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="80755-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="80755-108">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="80755-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="80755-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80755-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80755-110">Liczba współczynników, które mają zostać określone podczas przygotowywania stanu mieszanego.</span><span class="sxs-lookup"><span data-stu-id="80755-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="80755-111">Wynik: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="80755-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="80755-112">Opis liczby qubits wymaganych w sumie oraz dla każdego indeksu i rejestrów elementów bezużytecznych używanych przez @"microsoft.quantum.preparation.purifiedmixedstate" funkcję.</span><span class="sxs-lookup"><span data-stu-id="80755-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="80755-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="80755-113">See Also</span></span>

- [<span data-ttu-id="80755-114">Microsoft. Quantum. przygotowaniu. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="80755-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)