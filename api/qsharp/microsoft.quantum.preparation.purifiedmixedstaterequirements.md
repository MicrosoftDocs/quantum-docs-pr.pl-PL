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
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements, funkcja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca łączną liczbę qubits, które muszą zostać przydzielone w celu zastosowania operacji zwróconej przez @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Dane wejściowe

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Błąd elementu docelowego $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)

Liczba współczynników, które mają zostać określone podczas przygotowywania stanu mieszanego.



## <a name="output--mixedstatepreparationrequirements"></a>Wynik: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Opis liczby qubits wymaganych w sumie oraz dla każdego indeksu i rejestrów elementów bezużytecznych używanych przez @"microsoft.quantum.preparation.purifiedmixedstate" funkcję.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. przygotowaniu. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)