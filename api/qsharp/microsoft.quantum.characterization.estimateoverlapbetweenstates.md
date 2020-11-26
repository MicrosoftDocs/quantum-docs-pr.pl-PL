---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204304"
---
# <a name="estimateoverlapbetweenstates-operation"></a>EstimateOverlapBetweenStates, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku dwóch operacji, które każda przygotowuje kopie stanu, szacuje kwadratowe nakładanie się między Stanami przygotowanymi przez poszczególne operacje.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Pierwszy z dwóch operacji przygotowania stanu do porównania.


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Druga z dwóch operacji przygotowania stanu do porównania.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, na których `commonPreparation` , `preparation1` i `preparation2` wszystkie działania.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia podczas szacowania nakładania się.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

Ta operacja używa testu wymiany do znajdowania $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, gdzie $U $ jest reprezentacją jednostkową akcji `preparation1` i gdzie $V $ odpowiada `preparation2` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. charakteryzującą. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. charakteryzującą. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)