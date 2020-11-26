---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201805"
---
# <a name="equalityfactl-function"></a>EqualityFactL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że klasyczna zmienna BigInt ma oczekiwaną wartość.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--bigint"></a>rzeczywista: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba, która ma zostać sprawdzona.


### <a name="expected--bigint"></a>Oczekiwano: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Oczekiwana wartość.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Ciąg komunikatu o niepowodzeniu, który ma być używany, gdy potwierdzenie jest wyzwalane.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

