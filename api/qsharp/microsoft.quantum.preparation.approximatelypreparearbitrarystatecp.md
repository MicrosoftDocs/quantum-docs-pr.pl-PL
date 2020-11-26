---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: ApproximatelyPrepareArbitraryStateCP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 44352a4d6325c128539351695fb14d3706ce842f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226540"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a>ApproximatelyPrepareArbitraryStateCP, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Uwzględniając zestaw współczynników i zakodowany w formacie Quantum rejestr oparty na little-endian, przygotowuje stan tego rejestru opisany przez podane współczynniki, aż do danej przepuszczalnej tolerancji.

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta operacja przygotowuje dowolny stan Quantum $ \ket{\psi} $ z złożonymi współdziałami $r _j e ^ {i t_j} $ ze stanu podstawy obliczeń $n $-qubit $ \ket{0 \cdots 0} $.
W szczególności Akcja tej operacji może być symulowana przez transformację jednostkową $U $, która działa w stanie "wszystkie zero" jako

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Dane wejściowe

### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Tolerancja przybliżona, która ma być używana podczas przygotowywania danego stanu.


### <a name="coefficients--complexpolar"></a>współczynniki: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Tablica do $2 ^ n $ złożone współczynniki reprezentowane przez ich wartości bezwzględne i fazy $ (r_j, t_j) $. Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit rejestruje Stany kodowania w formacie little-endian. Oczekuje się, że zostanie ona zainicjowana w stanie bazowym obliczeniowym $ \ket{0...0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ujemne współczynniki wejścia $r _j < $0 będą traktowane jako wynik dodatni z wartością $ | r_j | $. `coefficients` zostanie uzupełniona o elementy $ (r_j, t_j) = (0,0, 0,0) $, jeśli określono mniej niż $2 ^ n $.

## <a name="references"></a>Odwołania

- Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176