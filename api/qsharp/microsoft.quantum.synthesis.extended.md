---
uid: Microsoft.Quantum.Synthesis.Extended
title: Funkcja rozszerzona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855470"
---
# <a name="extended-function"></a>Funkcja rozszerzona

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rozszerza spektrum przez odwrócone współczynniki

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="spectrum--int"></a>spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]

Współczynniki widma



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Współczynniki, po których następuje odwrócona kopia

## <a name="example"></a>Przykład

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```