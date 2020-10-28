---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716487"
---
# <a name="composedoutput-function"></a>ComposedOutput, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca dane wyjściowe kompozycji `inner` i `outer` dla danego danych wejściowych.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Dane wejściowe

### <a name="outer--u---v"></a>zewnętrzne: "U->" V




### <a name="inner--t---u"></a>wewnętrzny: brak > ' U




### <a name="target--t"></a>element docelowy: 'T





## <a name="output--v"></a>Wynik: ' V



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="u"></a>' U


### <a name="v"></a>"V

