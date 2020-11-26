---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206888"
---
# <a name="graycode-function"></a>GrayCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy szare sekwencje kodu

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów



## <a name="output--intint"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tablica krotek. Pierwsza wartość w spójnej kolekcji to wartość w sekwencji GrayCode drugiej wartości w spójnej lokalizacji, aby można ją było zmienić w bieżącej wartości.