---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714826"
---
# <a name="isnotzero-function"></a>IsNotZero, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Package [](https://nuget.org/packages/)


Sprawdza, czy `Double` liczba nie jest w przybliżeniu równa zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="number--double"></a>Liczba: [Double](xref:microsoft.quantum.lang-ref.double)

Liczba do sprawdzenia



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Zwraca wartość true, jeśli `number` ma wartość bezwzględną większą niż `1e-15` .