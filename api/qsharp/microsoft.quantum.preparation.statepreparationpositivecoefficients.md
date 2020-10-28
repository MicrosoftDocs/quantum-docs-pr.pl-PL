---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722894"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients, funkcja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Package [](https://nuget.org/packages/)


Zwraca operację, która przygotowuje dany stan Quantum.

Zwrócona operacja $U $ przygotowuje dowolny stan Quantum $ \ket{\psi} $ z pozytywnymi współczynnikimi $ \ alpha_j \ge $0 ze stanu podstawy obliczeń $n $-qubit $ \ket{0...0} $.

Akcja U w nowo przydzielonym rejestrze jest określona przez $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Tablica do $2 ^ n $ współczynniki $ \ alpha_j $. Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.



## <a name="output--littleendian--unit-adj--ctl"></a>Dane wyjściowe: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL

Operacja jednostki przygotowania stanu $U $.

## <a name="remarks"></a>Uwagi

Ujemne współczynniki danych wejściowych $ \ alpha_j < $0 będą traktowane jako wynik dodatni z wartością $ | \ alpha_j | $. `coefficients` zostanie uzupełniona o elementy $ \ alpha_j = $0,0, jeśli określono mniej niż $2 ^ n $.