---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824399"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dla danej tabeli operacji Pauli w danym rejestrze qubits, ta funkcja zwraca obiekt typu `RecoveryFn` , który zawiera wszystkie informacje, które są konieczne do wykonania dekodowania wyszukiwania w tabeli w odniesieniu do danej tablicy operacji Pauli.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Dane wejściowe

### <a name="table--pauli"></a>Tabela: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabela operacji Pauli, które działają na danym rejestrze qubit



## <a name="output--recoveryfn"></a>Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Obiekt typu `RecoveryFn` , czyli mapa, `Syndrome -> Pauli[]` która jest skojarzona z daną tablicą Syndrome odpowiednią operacją korekcji Pauli.