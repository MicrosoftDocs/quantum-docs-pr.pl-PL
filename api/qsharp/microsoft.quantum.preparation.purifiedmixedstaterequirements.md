---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229991"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="2d32b-102">PurifiedMixedStateRequirements, funkcja</span><span class="sxs-lookup"><span data-stu-id="2d32b-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="2d32b-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2d32b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2d32b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d32b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d32b-105">Zwraca łączną liczbę qubits, które muszą zostać przydzielone w celu zastosowania operacji zwróconej przez @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="2d32b-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="2d32b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2d32b-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="2d32b-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d32b-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d32b-108">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="2d32b-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="2d32b-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d32b-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d32b-110">Liczba współczynników, które mają zostać określone podczas przygotowywania stanu mieszanego.</span><span class="sxs-lookup"><span data-stu-id="2d32b-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="2d32b-111">Wynik: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="2d32b-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="2d32b-112">Opis liczby qubits wymaganych w sumie oraz dla każdego indeksu i rejestrów elementów bezużytecznych używanych przez @"microsoft.quantum.preparation.purifiedmixedstate" funkcję.</span><span class="sxs-lookup"><span data-stu-id="2d32b-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d32b-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2d32b-113">See Also</span></span>

- [<span data-ttu-id="2d32b-114">Microsoft. Quantum. przygotowaniu. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="2d32b-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)