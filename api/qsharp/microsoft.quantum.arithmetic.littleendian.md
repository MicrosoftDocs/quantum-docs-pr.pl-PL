---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222783"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności little-endian. Qubit z indeksem `0` koduje najniższy bit liczby całkowitej bez znaku.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Uwagi

Skracamy `LittleEndian` `LE` się w dokumentacji.