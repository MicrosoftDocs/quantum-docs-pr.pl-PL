---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720405"
---
# <a name="realmod-function"></a>RealMod, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Oblicza moduł między dwoma liczbami rzeczywistymi.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="value--double"></a>wartość: [Double](xref:microsoft.quantum.lang-ref.double)

Liczba rzeczywista $x $, aby pobrać moduł.


### <a name="modulo--double"></a>modulo: [Double](xref:microsoft.quantum.lang-ref.double)

Liczba rzeczywista, która przyjmuje moduł $x $ w odniesieniu do.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Najmniejsza wartość, która ma zostać zwrócona przez tę funkcję.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

Ta funkcja oblicza moduł rzeczywisty, zawijając linię rzeczywistą wokół okręgu jednostki, a następnie wyszukując kąt w okręgu jednostki odpowiadającym danym wejściowym.
`minValue`Następnie dane wejściowe określają, gdzie należy wyciąć okrąg jednostkowy.