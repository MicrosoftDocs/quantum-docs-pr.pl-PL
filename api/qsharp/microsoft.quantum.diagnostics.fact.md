---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Funkcja faktów
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853320"
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



## <a name="example"></a>Przykład

Poniższy fragment kodu Q # zakończy się niepowodzeniem:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. dosprzeczność](xref:Microsoft.Quantum.Diagnostics.Contradiction)