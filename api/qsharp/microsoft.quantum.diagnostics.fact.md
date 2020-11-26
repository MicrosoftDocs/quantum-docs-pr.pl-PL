---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funkcja faktów
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201686"
---
# <a name="fact-function"></a>Funkcja faktów

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Deklaruje, że klasyczny warunek ma wartość true.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--bool"></a>rzeczywista: [bool](xref:microsoft.quantum.lang-ref.bool)

Warunek, który ma zostać zadeklarowany.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Ciąg komunikatu o niepowodzeniu do wydrukowania w przypadku, gdy klasyczny warunek ma wartość false.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. dosprzeczność](xref:Microsoft.Quantum.Diagnostics.Contradiction)