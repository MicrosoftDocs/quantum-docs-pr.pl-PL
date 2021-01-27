---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843396"
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