---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Funkcja sprzeczności
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202145"
---
# <a name="contradiction-function"></a>Funkcja sprzeczności

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Deklaruje, że klasyczny warunek ma wartość false.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--bool"></a>rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)

Warunek, który ma zostać zadeklarowany.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość true.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. fakt](xref:Microsoft.Quantum.Diagnostics.Fact)