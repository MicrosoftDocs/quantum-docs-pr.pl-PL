---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223667"
---
# <a name="bigendian-user-defined-type"></a>BigEndian typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności big-endian. Qubit z indeksem `0` koduje największą liczbę liczb całkowitych bez znaku.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Uwagi

Skracamy `BigEndian` `BE` się w dokumentacji.