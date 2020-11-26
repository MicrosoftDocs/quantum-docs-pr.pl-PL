---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: Funkcja _ComputeJordanWignerBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203947"
---
# <a name="_computejordanwignerbitstring-function"></a>Funkcja _ComputeJordanWignerBitString

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Oblicza składnik Z programu Jordanii — ciąg Wigner między indeksami Fermion w operatorze fermionic z parzystą liczbą operatorów tworzenia i Annihilation.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Dane wejściowe

### <a name="nfermions--int"></a>nFermions: [int](xref:microsoft.quantum.lang-ref.int)

Liczba fermions w systemie.


### <a name="idxfermions--int"></a>idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]

indeksy operatora fermionic.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitstring `Bool[]` , `true` w którym `PauliZ` należy zastosować.