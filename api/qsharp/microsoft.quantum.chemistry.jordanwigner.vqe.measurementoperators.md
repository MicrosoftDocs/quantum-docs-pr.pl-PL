---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214351"
---
# <a name="measurementoperators-function"></a>MeasurementOperators, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Oblicza wszystkie operatory pomiarów wymagane do obliczenia oczekiwania Jordan-Wigner warunku.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits wymaganych do symulowania systemu cząsteczkowego.


### <a name="indices--int"></a>indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica zawierająca indeksy qubit każdy operator Pauli jest stosowany do.


### <a name="termtype--int"></a>termtype: [int](xref:microsoft.quantum.lang-ref.int)

Typ warunku Jordan-Wigner.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tablica operatorów pomiarów (każda jest tablicą Pauli).