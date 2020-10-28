---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721221"
---
# <a name="dividei-operation"></a>DivideI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Dzieli dwie liczby całkowite jednostek Quantum.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

`xs` pozostanie resztę `xs - floor(xs/ys) * ys` i `result` zostanie wstrzymane `floor(xs/ys)` .

## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$na dywidenda $-bitowa zostanie zastąpiona resztą.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n dzielnika $-bitowego


### <a name="result--littleendian"></a>wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

wyniki $n $-bit muszą być w stanie $ \ket {0} $ początkowo i zostaną zastąpione przez wynik dzielenia liczb całkowitych.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Stosuje standardowe podejście Shift-and-odejmowanie do wdrożenia dzielenia.
Kontrolowana wersja jest wyspecjalizowana, co oznacza, że odejmowanie nie wymaga dodatkowych kontroli.