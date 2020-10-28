---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712348"
---
# <a name="encodeop-user-defined-type"></a>EncodeOp typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Reprezentuje operację, która koduje fizyczny rejestr do rejestru logicznego przy użyciu dostarczonej qubits.

Pierwszy argument jest traktowany jako rejestr fizyczny, który zostanie zakodowany, natomiast drugi argument jest traktowany jako rejestr, który zostanie użyty.

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

