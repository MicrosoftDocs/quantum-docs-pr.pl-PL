---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851882"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mając na celu przygotowanie i pomiar, szacuje częstotliwość, z jaką pomiar zakończy się powodzeniem (zwraca `Zero` ), wykonując daną liczbę prób.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="preparation--qubit--unit"></a>Przygotowanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja $P $, która przygotowuje dane stanu $ \rho $ w rejestrze wejściowym.


### <a name="measurement--qubit--__invalidresult__"></a>Pomiar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __nieprawidłowy <Result>__ 

Operacja $M $ reprezentująca miarę zainteresowania.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, na których przygotowanie i pomiar każdego działania.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba przypadków, w których pomiar ma być wykonywany w celu oszacowania częstotliwości zainteresowania.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Oszacowanie $ \hat{p} $ częstotliwości, z którą $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ zwraca `Zero` , uzyskany przy użyciu nieobciążonego dwumianu, szacowania $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{measurements}} $, gdzie $n \_ {\uparrow} $ to liczba `Zero` zaobserwowanych wyników.

Jest to szczególnie ważne w przypadku maszyn docelowych, które respektują ograniczenia fizyczne, tak że nie można mierzyć prawdopodobieństwa.