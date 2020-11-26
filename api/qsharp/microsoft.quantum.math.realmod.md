---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228257"
---
# <a name="realmod-function"></a>RealMod, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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