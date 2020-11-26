---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192064"
---
# <a name="applypermutationusingtransformation-operation"></a>ApplyPermutationUsingTransformation, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na transformacji.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta procedura implementuje jednokierunkowe podejście syntezy opartej na transformacji.  Dane wejściowe to Permutacja $ \pi $ przez $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, która reprezentuje $n $-Variable odwracalnej funkcji logicznej.
Algorytm wykonuje iteracyjnie następujące czynności:

1. Znajdź najmniejszy $x $ taki, który $x \ne \pi (x) = y $.
2. Znajdź wielokontrolowane operacje Toffoli, które mają zastosowanie do danych wyjściowych $ \pi (x) = x $ i nie zmieniaj $ \pi (x ') $ dla wszystkich $x "< x $

## <a name="input"></a>Dane wejściowe

### <a name="perm--int"></a>uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutacja elementów $2 ^ n $ zaczynających się od 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Lista $n $ qubits, do której zostanie zastosowana Permutacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Odwołania

- [*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, PP. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, PP. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. synteza. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)