---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721044"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności little-endian. Qubit z indeksem `0` koduje najniższy bit liczby całkowitej bez znaku.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Uwagi

Skracamy `LittleEndian` `LE` się w dokumentacji.