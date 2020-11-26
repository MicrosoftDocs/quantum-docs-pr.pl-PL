---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202213"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Potwierdza, że element qubit w oczekiwanym stanie.

`expected` reprezentuje złożony wektor, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
Pierwszy element spójnych krotek reprezentuje każdy z $a $, $b $ jest rzeczywistą częścią liczby zespolonej, a druga jest częścią urojoną.
Ostatni argument definiuje tolerancję, z którą jest wykonywane potwierdzenie.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="expected--complexcomplex"></a>oczekiwana: ([złożona](xref:Microsoft.Quantum.Math.Complex),[złożona](xref:Microsoft.Quantum.Math.Complex))

Oczekiwane są odpowiednio złożone amplitudy dla elementów $ \ket {0} $ i $ \ket {1} $.


### <a name="register--qubit"></a>Zarejestruj się: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, którego stan ma zostać potwierdzony. Należy zauważyć, że ta qubit jest traktowana jako oddzielna od innych przyznanych qubits, a nie Entangled.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Tolerancja dodatku, według którego rzeczywiste Amplitude mogą odbiegać od oczekiwanego.
Aby uzyskać szczegółowe informacje, zobacz uwagi poniżej.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Następujący kod Mathematica może służyć do weryfikowania wyrażeń dla mi, MX, my, MZ:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

Tolerancja to $L \_ {\infty} $, odległość między trójwymiarową wektorem rzeczywistym (x ₂, x ₃, x ₄) zdefiniowane przez $ \langle\psi | \psi\rangle = x \_ 1 i + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ i Real Vector (y ₂, y ₃, y ₄) zdefiniowane przez ρ = y ₁ i + y ₂ x + y ₃ y + y ₄ z, gdzie ρ jest matrycą gęstości odpowiadającą stanowi rejestru.
Jest to tylko prawdziwe w założeniu, że TR (ρ) i TR (| ψ ⟩ ⟨ ψ |) są zarówno 1 (np. x ₁ = 1/2, y ₁ = 1/2).
Jeśli tak się nie dzieje, funkcja potwierdza, że odległość l ∞ między (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) i (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) jest mniejsza niż parametr tolerancji.