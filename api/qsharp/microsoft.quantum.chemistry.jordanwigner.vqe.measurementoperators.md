---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713678"
---
# <a name="measurementoperators-function"></a>MeasurementOperators, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Package [](https://nuget.org/packages/)


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