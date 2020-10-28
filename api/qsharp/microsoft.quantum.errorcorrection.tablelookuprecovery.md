---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712049"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Dla danej tabeli operacji Pauli w danym rejestrze qubits, ta funkcja zwraca obiekt typu `RecoveryFn` , który zawiera wszystkie informacje, które są konieczne do wykonania dekodowania wyszukiwania w tabeli w odniesieniu do danej tablicy operacji Pauli.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Dane wejściowe

### <a name="table--pauli"></a>Tabela: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabela operacji Pauli, które działają na danym rejestrze qubit



## <a name="output--recoveryfn"></a>Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Obiekt typu `RecoveryFn` , czyli mapa, `Syndrome -> Pauli[]` która jest skojarzona z daną tablicą Syndrome odpowiednią operacją korekcji Pauli.