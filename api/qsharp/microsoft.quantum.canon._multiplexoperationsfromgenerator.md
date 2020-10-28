---
uid: Microsoft.Quantum.Canon._MultiplexOperationsFromGenerator
title: Operacja _MultiplexOperationsFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: _MultiplexOperationsFromGenerator
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 17d8f3e9b800e26a00969418ca061e3ea1d97682
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718509"
---
# <a name="_multiplexoperationsfromgenerator-operation"></a>Operacja _MultiplexOperationsFromGenerator

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Krok implementacji elementu `MultiplexOperationsFromGenerator` .

```qsharp
operation _MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="unitarygenerator--intintint---t--unit-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL)




### <a name="auxiliary--qubit"></a>pomocniczy: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>element docelowy: 'T





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)