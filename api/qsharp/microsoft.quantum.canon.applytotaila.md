---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207925"
---
# <a name="applytotaila-operation"></a>ApplyToTailA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację do ostatniego elementu tablicy.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Opis

`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-adj"></a>op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja, która ma zostać zastosowana.


### <a name="targets--t"></a>elementy docelowe: t []

Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać zastosowana.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. Quantum. Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. Quantum. Canon. ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)