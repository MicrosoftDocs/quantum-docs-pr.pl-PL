---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207041"
---
# <a name="embedpauli-function"></a>EmbedPauli, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Za pomocą pojedynczego operatora Pauli qubit i indeksu qubit, zwraca wieloqubity operator Pauli z danym operatorem Single-qubit w tym indeksie i `PauliI` w każdym innym indeksie.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Dane wejściowe

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Qubit operator Pauli, który ma zostać umieszczony w danej lokalizacji.


### <a name="location--int"></a>Lokalizacja: [int](xref:microsoft.quantum.lang-ref.int)

Indeks taki `output[location] == pauli` , gdzie `output` jest danymi wyjściowymi tej funkcji.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Długość tablicy, która ma zostać zwrócona.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

