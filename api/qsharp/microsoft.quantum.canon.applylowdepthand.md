---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 092a350e42d8d90942de13530fefd761b5187e1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717985"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Odwraca podaną wartość docelową qubit, jeśli i tylko wtedy, gdy oba kontrolki qubits są w stanie 1, z głębokością T 1, przy użyciu miary do wykonania sąsiedniej operacji.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Opis

Odwraca, `target` czy i tylko wtedy, gdy obie kontrolki są 1, ale zakłada, że `target` jest w stanie 0.  Operacja ma wartość T-Count 4, T-głębokość 1 i wymaga jednego pomocnika qubit i dlatego może być zalecana dla operacji CCNOT, jeśli `target` jest znana jako 0.  Sąsiednia operacja jest oparta na pomiarach i nie wymaga żadnych bram T i nie qubit pomocnika.

## <a name="input"></a>Dane wejściowe

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy formant qubit


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druga kontrolka qubit


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Docelowa qubit pomocnicza; musi być w stanie 0



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- Cody Nowak: "Nowa konstrukcja dla bramy Toffoli odpornej na uszkodzenia", biorev. obr. A 87, 022328, 2013 [ArXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Piotr Selinger: "" Quantum obwodów "T-głębokości" i "," Bio. Rev. A 87, 042302, 2013 [ArXiv: 1210.0974](https://arxiv.org/abs/1210.0974) DOI: 10.1103/PhysRevA. 87.042302