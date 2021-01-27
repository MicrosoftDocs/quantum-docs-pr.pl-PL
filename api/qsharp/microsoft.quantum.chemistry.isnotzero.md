---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839602"
---
# <a name="isnotzero-function"></a>IsNotZero, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Sprawdza, czy `Double` liczba nie jest w przybliżeniu równa zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="number--double"></a>Liczba: [Double](xref:microsoft.quantum.lang-ref.double)

Liczba do sprawdzenia



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Zwraca wartość true, jeśli `number` ma wartość bezwzględną większą niż `1e-15` .