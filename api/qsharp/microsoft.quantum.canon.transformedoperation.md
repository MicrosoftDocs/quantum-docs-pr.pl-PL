---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852051"
---
# <a name="transformedoperation-function"></a>TransformedOperation, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana funkcja i operacja zwracają nową operację, której dane wejściowe są przekształcane przez daną funkcję.

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="fn--u---t"></a>fn: "U-> t

Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.


### <a name="op--t--unit"></a>op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać przekształcona.



## <a name="output--u--unit"></a>Wynik: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Nowa operacja tbat wywołania `fn` z danymi wejściowymi, a następnie przekazuje wynikowe dane wyjściowe do `op` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="u"></a>' U



## <a name="example"></a>Przykład

Poniższe wywołanie używa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" do przekształcenia operacji przeznaczonej do wprowadzania @"Microsoft.Quantum.Arithmetic.BigEndian" danych wejściowych do operacji akceptującej dane wejściowe typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. złożona](xref:Microsoft.Quantum.Canon.Composed)