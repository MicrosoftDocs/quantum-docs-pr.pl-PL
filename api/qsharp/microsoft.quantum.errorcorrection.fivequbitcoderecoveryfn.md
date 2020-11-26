---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200785"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca funkcję, która mapuje Syndrome błędów do odpowiednich operatorów Pauliych w celu poprawienia błędów przez wyszukiwanie w tabeli dla kodu ⟦ 5, 1, 3 ⟧.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Funkcja typu `RecoveryFn` , która przyjmuje pomiar Syndrome `Result[]` i zwraca `Pauli[]` operatory, które korygują wykryty błąd.

## <a name="remarks"></a>Uwagi

Przez iterację wszystkich błędów wag $1 $ uzyskamy łącznie $3 \ Times 5 = 15 $ możliwe nieuproszczony Syndromes.
Wraz z tożsamością, tabela błędu i odpowiadające Syndrome są kompilowane. Dla kodu 5 qubit ta tabela jest podawana: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ z $Y _i $ uzyskane przez dodanie $X _i $ i $Z _i $ Syndromes. Należy zauważyć, że kolejność w odnośniku wyszukiwania tabeli jest wyrażana przez konwersję bitvectors na liczby całkowite (przy użyciu little endian).

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)