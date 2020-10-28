---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721281"
---
# <a name="comparegtsi-operation"></a>CompareGTSI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Otoka dla porównań ze znakiem liczby całkowitej: `result = xs > ys` .

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Numer pierwszej $n $-bitowy


### <a name="ys--signedlittleendian"></a>YS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Druga $n $-bit Number


### <a name="result--qubit"></a>wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Zostanie przerzucony, jeśli $xs > YS $



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

