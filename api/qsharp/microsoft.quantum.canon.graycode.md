---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716165"
---
# <a name="graycode-function"></a>GrayCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Tworzy szare sekwencje kodu

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów



## <a name="output--intint"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tablica krotek. Pierwsza wartość w spójnej kolekcji to wartość w sekwencji GrayCode drugiej wartości w spójnej lokalizacji, aby można ją było zmienić w bieżącej wartości.