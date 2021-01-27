---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850561"
---
# <a name="applytomostc-operation"></a>ApplyToMostC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Opis

`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-ctl"></a>op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

Operacja, która ma zostać zastosowana.


### <a name="targets--t"></a>elementy docelowe: t []

Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać zastosowana.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. Quantum. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. Quantum. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)