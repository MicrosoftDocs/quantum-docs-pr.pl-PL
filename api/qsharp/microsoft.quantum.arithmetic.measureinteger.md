---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720969"
---
# <a name="measureinteger-operation"></a>MeasureInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Mierzy zawartość rejestru Quantum i konwertuje ją na liczbę całkowitą. Pomiary są wykonywane w odniesieniu do standardowej obliczeń, tj. eigenbasis `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="target--littleendian"></a>obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum w kodowaniu little-endian.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita bez znaku, która zawiera mierzoną wartość `target` .

## <a name="remarks"></a>Uwagi

Ta operacja resetuje swój rejestr wejściowy do stanu $ \ket{00\cdots 0} $, który jest odpowiedni do wydawania z powrotem do maszyny docelowej.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)