---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201839"
---
# <a name="equalityfacti-function"></a>EqualityFactI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że klasyczna zmienna int ma oczekiwaną wartość.

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--int"></a>rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)

Liczba, która ma zostać sprawdzona.


### <a name="expected--int"></a>Oczekiwano: [int](xref:microsoft.quantum.lang-ref.int)

Oczekiwana wartość.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

