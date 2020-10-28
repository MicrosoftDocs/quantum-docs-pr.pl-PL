---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716338"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca operację implementującą Integrator Trotter – Suzuki dla danej operacji.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

Liczba operacji do rozdzielenia na etapy czasu.


### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) dla dekompozycji.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Wybiera kolejność użycia integratora Trotter – Suzuki.
Kolejność 1, a nawet Orders 2, 4, 6,... są obecnie obsługiwane.



## <a name="output--doublet--unit-adj--ctl"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Zwraca jednostkę implementującą Integrator Trotter – Suzuki, gdzie pierwszy parametr `Double` jest rozmiarem kroku integracji, a drugi parametr jest celem działania.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .

## <a name="remarks"></a>Uwagi

Gdy jest wywoływana z `order` równa `1` , ta funkcja zwraca operację, która może być symulowana przez Trottere — Integrator Suzuki $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, w którym zastosowano notację [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) i niech $ \lambda $ to czas ewolucji (reprezentowany przez pierwsze wejście operacji zwróconej), i mieć \{ wartość $ H_j \} _ {j = 1} ^ {m} $ to zestaw (skośny hermitian), które są zintegrowane, które `op(j, lambda, _)` są symulowane przez operatora jednostki $e ^ {H_j \lambda} $.

Analogicznie, `order` element `2` zwraca w drugim porządku symetryczne Trotter — Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

Wyższe wartości równe `order` są implementowane przy użyciu cyklicznej konstrukcji [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Dokumentacja

- [*D. W. owoce jagodowe, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)