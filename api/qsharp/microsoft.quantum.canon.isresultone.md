---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206548"
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