---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201771"
---
# <a name="equalityfactr-function"></a>EqualityFactR, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że klasyczna zmienna wynikowa ma oczekiwaną wartość.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--__invalidresult__"></a>rzeczywiste: __nieprawidłowe <Result>__

Zmienna, która ma zostać sprawdzona.


### <a name="expected--__invalidresult__"></a>Oczekiwano __: <Result> nieprawidłowe__

Oczekiwana wartość.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

