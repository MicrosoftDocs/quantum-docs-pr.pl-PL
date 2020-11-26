---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204355"
---
# <a name="estimatefrequencya-operation"></a>EstimateFrequencyA, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Na podstawie przygotowania, które jest sąsiednie i pomiarowe, szacuje częstotliwość, z jaką ten pomiar zakończy się powodzeniem (zwraca `Zero` ), wykonując daną liczbę prób.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="preparation--qubit--unit--is-adj"></a>Przygotowanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja współdziałania $P $, która przygotowuje dany stan $ \rho $ na swój rejestr wejściowy.


### <a name="measurement--qubit--__invalidresult__"></a>Pomiar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __nieprawidłowy <Result>__ 

Operacja $M $ reprezentująca miarę zainteresowania.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, na których przygotowanie i pomiar każdego działania.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba przypadków, w których pomiar ma być wykonywany w celu oszacowania częstotliwości zainteresowania.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Oszacowanie $ \hat{p} $ częstotliwości, z którą $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ zwraca `Zero` , uzyskany przy użyciu nieobciążonego dwumianu, szacowania $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{measurements}} $, gdzie $n \_ {\uparrow} $ to liczba `Zero` zaobserwowanych wyników.

## <a name="remarks"></a>Uwagi

W przypadku operacji współdziałania niektóre założenia mogą zostać wykonane, takie jak wywołanie operacji, przygotuje qubits do tego samego stanu, co umożliwi maszynom docelowym wykonywanie niektórych optymalizacji wydajności.