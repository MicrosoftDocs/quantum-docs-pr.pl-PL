---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203437"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>ApplyPermutationUsingDecompositionWithVariableOrder, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta operacja jest bardziej ogólną wersją, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" w której można określić kolejność zmiennych. Inna kolejność zmiennych zmienia sekwencję dekompozycji i tabele prawdy używane dla bram sterowanych @"microsoft.quantum.intrinsic.x" .  W związku z tym zmiana kolejności zmiennych zmienia liczbę ogólnych bram używanych do realizacji permutacji.

## <a name="input"></a>Dane wejściowe

### <a name="perm--int"></a>uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutacja elementów $2 ^ n $ zaczynających się od 0.


### <a name="variableorder--int"></a>variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutacja $n $ elementów rozpoczynając od 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Lista $n $ qubits, do której zostanie zastosowana Permutacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. synteza. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)