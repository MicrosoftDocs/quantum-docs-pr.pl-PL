---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203318"
---
# <a name="applytransposition-operation"></a>ApplyTransposition, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta operacja zamienia amplitudę na indeks `a` z amplitudą przy indeksie `b` w danym stanie-Vector o `register` długości $n $.  Jeśli `a` jest równe `b` , wektor stanu nie jest zmieniany.

## <a name="input"></a>Dane wejściowe

### <a name="a--int"></a>Odp.: [int](xref:microsoft.quantum.lang-ref.int)

Pierwszy indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Drugi indeks (musi być wartością z przestawu od 0 do $2 ^ n-$1)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Lista $n $ qubits, do której zostanie zastosowana transpozycja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

