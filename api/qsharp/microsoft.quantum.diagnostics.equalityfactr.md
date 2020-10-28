---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712740"
---
# <a name="equalityfactr-function"></a>EqualityFactR, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


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

