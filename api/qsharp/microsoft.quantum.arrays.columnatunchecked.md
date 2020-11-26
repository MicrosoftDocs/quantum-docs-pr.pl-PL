---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221593"
---
# <a name="columnatunchecked-function"></a>ColumnAtUnchecked, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ta funkcja nie sprawdza dla kształtu macierzy

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Opis

Ta funkcja może być używana w innych funkcjach wielowymiarowych, które już sprawdzają macierz wejściową dla prawidłowego prostokątnego kształtu.

## <a name="input"></a>Dane wejściowe

### <a name="column--int"></a>kolumna: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="matrix--t"></a>Macierz: t [] []





## <a name="output--t"></a>Wynik: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

