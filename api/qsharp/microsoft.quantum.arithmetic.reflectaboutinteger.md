---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719712"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Odzwierciedla rejestr Quantum o danej klasycznej liczbie całkowitej.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Zgodnie z wstępnym rejestrem Quantum w stanie $ \ sum_i \ alpha_i \ket{i} $, gdzie każdy $ \ket{i} $ jest stanem bazowym reprezentującym liczbę całkowitą $i $, odzwierciedla stan rejestru o stanie bazowym dla danej liczby całkowitej $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Dane wejściowe

### <a name="index--int"></a>indeks: [int](xref:microsoft.quantum.lang-ref.int)

Klasyczna liczba całkowita — indeksowanie stanu podstawy, które należy uwzględnić.


### <a name="reg--littleendian"></a>reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja jest zaimplementowana w miejscu bez jawnego przydziału dodatkowych pomocniczych qubits.