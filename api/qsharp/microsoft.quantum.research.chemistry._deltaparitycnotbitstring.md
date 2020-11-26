---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funkcja _DeltaParityCNOTbitstring
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226081"
---
# <a name="_deltaparitycnotbitstring-function"></a>Funkcja _DeltaParityCNOTbitstring

Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)

Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Etap klasycznego przetwarzania `ApplyDeltaParity` .
To oblicza listę qubits kontroli do oceny różnicy parzystości między dowolnymi dwoma PQRS... warunki nawet długości.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Dane wejściowe

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Uwagi

Przyjęto założenie, że długość warunków jest parzysta.
Oblicza listę kontrolek z różnicą parzystości między dowolnym z dwóch warunków.
Przyjęto założenie, że listy wejściowe są sortowane w kolejności rosnącej.