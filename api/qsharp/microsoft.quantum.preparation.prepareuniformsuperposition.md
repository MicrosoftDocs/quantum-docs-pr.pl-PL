---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854317"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy jednolity nadpozycja w stosunku do Stanów, które kodują od 0 do `nIndices - 1` .

Oznacza to, że ta jednostka $U $ tworzy jednolity nadpozycja dla wszystkich stanów $0 $ do $M-$1, z uwzględnieniem stanu wejściowego $ \ket{0\cdots 0} $. Innymi słowy, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Wymagana liczba Stanów $M $ w jednolitej lokalizacji.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr qubit, który przechowuje liczbę stanów w `LittleEndian` formacie.
Ten rejestr musi być w stanie przechowywać liczbę $M-$1 i założono, że zostanie zainicjowany w stanie $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Przykład

Poniższy przykład przygotowuje stan $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ on $3 $ qubits.

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>Uwagi

Operacja jest Współrzędna, ale wymaga, aby `indexRegister` w tym przypadku w pierwszej kolejności były w jednolity sposób `nIndices` .