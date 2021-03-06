---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840682"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operację implementującą Integrator Trotter – Suzuki dla danej operacji.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

Liczba operacji do rozdzielenia na etapy czasu.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) dla dekompozycji.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Wybiera kolejność użycia integratora Trotter – Suzuki.
Kolejność 1, a nawet Orders 2, 4, 6,... są obecnie obsługiwane.



## <a name="output--doublet--unit--is-adj--ctl"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Zwraca jednostkę implementującą Integrator Trotter – Suzuki, gdzie pierwszy parametr `Double` jest rozmiarem kroku integracji, a drugi parametr jest celem działania.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .

## <a name="remarks"></a>Uwagi

Gdy jest wywoływana z `order` równa `1` , ta funkcja zwraca operację, która może być symulowana przez Trottere — Integrator Suzuki $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, w którym zastosowano notację [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) i niech $ \lambda $ to czas ewolucji (reprezentowany przez pierwsze wejście operacji zwróconej), i mieć \{ wartość $ H_j \} _ {j = 1} ^ {m} $ to zestaw (skośny hermitian), które są zintegrowane, które `op(j, lambda, _)` są symulowane przez operatora jednostki $e ^ {H_j \lambda} $.

Analogicznie, `order` element `2` zwraca w drugim porządku symetryczne Trotter — Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

Wyższe wartości równe `order` są implementowane przy użyciu cyklicznej konstrukcji [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Odwołania

- [*D. W. owoce jagodowe, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)