---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721116"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Potwierdź, że wszystkie liczby stałych punktów w podanej tablicy mają identyczne położenia punktów podczas zliczania z najmniej znaczącego bitu. Oznacza to, że liczba pozycji punktu minusa bity musi być stała dla wszystkich liczb stałych punktów w tablicy.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="fixedpoints--fixedpoint"></a>fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

Tablica liczb stałych zmiennoprzecinkowych, które będą sprawdzane pod kątem zgodności (przy użyciu potwierdzeń).



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

