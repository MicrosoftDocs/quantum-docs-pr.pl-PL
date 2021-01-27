---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842975"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Odzwierciedla rejestr Quantum o danej klasycznej liczbie całkowitej.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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