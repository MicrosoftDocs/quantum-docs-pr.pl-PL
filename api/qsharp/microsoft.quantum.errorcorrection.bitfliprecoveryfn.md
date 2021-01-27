---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827595"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Funkcja dla operacji odzyskiwania Pauli dla danego pomiaru Syndrome przez wyszukiwanie w tabeli dla kodu przewrócenia ⟦ 3, 1, 1 ⟧.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Funkcja typu `RecoveryFn` , która przyjmuje pomiar Syndrome `Result[]` i zwraca `Pauli[]` operacje, które korygują wykryty błąd.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)