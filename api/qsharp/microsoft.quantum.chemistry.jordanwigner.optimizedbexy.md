---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713911"
---
# <a name="optimizedbexy-operation"></a>OptimizedBEXY, operacja

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package [](https://nuget.org/packages/)


Jednostkowa $U $, która stosuje ciąg Pauli w $ (X ^ {z + 1} z \_ PR ^ {z} \_ p) z \_ {p-1}... Z_0 $ qubits $0.. p $ Conditional na indeksie $z \In \{ 0, 1 \} $ i $p $. Oznacza to, że $ $ \begin{align} U\ket {z} \ KET {p} \ KET {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} z \_ PR ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="paulibasis--qubit"></a>pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Gdy qubit jest w stanie $ \ket {0} $, zostanie zastosowany $X $. Gdy jest w stanie $ \ket {1} $, zostanie zastosowany $Y $.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Stan $ \ket{p} $ tej rejestracji określa qubit, na których zastosowano $X $ lub $Y $.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr elementu qubits, na którym są stosowane operatory Pauli.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662