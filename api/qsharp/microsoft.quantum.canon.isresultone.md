---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840324"
---
# <a name="isresultone-function"></a>IsResultOne, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Testuje, czy dana wartość wynikowa jest równa `One` .

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="input--__invalidresult__"></a>dane wejściowe __: <Result> nieprawidłowe__

`Result` wartość do przetestowania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Zwraca `true` wartość `input` , jeśli jest równa `One` .