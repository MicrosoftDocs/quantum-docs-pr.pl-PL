---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725316"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Package [](https://nuget.org/packages/)


Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Ta procedura implementuje podejście syntezy opartej na dekompozycji.  Dane wejściowe to Permutacja $ \pi $ przez $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, która reprezentuje $n $-Variable odwracalnej funkcji logicznej.
Algorytm iteracyjnie wykonuje następujące kroki dla każdego indeksu zmiennych $i $:

1. COMPUTE $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.
2. Ustaw wartość $ \pi \leftarrow \pi "$" i Utwórz tabele prawdy z $ \ pi_l $ i $ \ pi_r $ na podstawie elementów, które nie są stałymi punktami.

Po zastosowaniu tych kroków dla wszystkich indeksów zmiennych, pozostała Permutacja $ \pi $ będzie tożsamość, a na podstawie zebranych tabel i indeksów prawdy można zastosować operacje kontrolowane w tabeli prawdy @"microsoft.quantum.intrinsic.x" przy użyciu @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operacji.

Zmienna Order to $0, \dots, n-$1.  W operacji można określić kolejność zmiennych niestandardowych @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Dane wejściowe

### <a name="perm--int"></a>uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutacja elementów $2 ^ n $ zaczynających się od 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Lista $n $ qubits, do której zostanie zastosowana Permutacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- [*Alexis de Vos* , *Yvan van Rentergem* , ADV. in Math. of Communication. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , arkusz obliczeń symbolicznych 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. synteza. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)