---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714975"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>EstimateRealOverlapBetweenStates, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Package [](https://nuget.org/packages/)


Dwie operacje, które każdy przygotują kopie stanu, szacują rzeczywistą część nakładania się między Stanami przygotowanymi przez poszczególne operacje.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja, która przygotowuje stały stan wejściowy.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Pierwszy z dwóch operacji przygotowania stanu do porównania.


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Druga z dwóch operacji przygotowania stanu do porównania.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, na których `commonPreparation` , `preparation1` i `preparation2` wszystkie działania.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia podczas szacowania nakładania się.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

Ta operacja używa testu Hadamard, aby znaleźć rzeczywistą część $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $, gdzie $ \ket{\psi} $ jest stanem przygotowanym przez `commonPreparation` , $U $ jest reprezentacją jednostkową akcji `preparation1` i gdzie $V $ odpowiada `preparation2` .

## <a name="references"></a>Dokumentacja

- Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. charakteryzującą. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft. Quantum. charakteryzującą. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)