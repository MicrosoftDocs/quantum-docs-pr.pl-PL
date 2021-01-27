---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848343"
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



## <a name="example"></a>Przykład

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Uwagi

Ta funkcja oblicza moduł rzeczywisty, zawijając linię rzeczywistą wokół okręgu jednostki, a następnie wyszukując kąt w okręgu jednostki odpowiadającym danym wejściowym.
`minValue`Następnie dane wejściowe określają, gdzie należy wyciąć okrąg jednostkowy.