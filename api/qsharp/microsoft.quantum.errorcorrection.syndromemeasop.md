---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200258"
---
# <a name="syndromemeasop-user-defined-type"></a>SyndromeMeasOp typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje operację, która jest używana do mierzenia Syndrome w bloku kodu z korekcją błędów.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Uwagi

Sygnatura `(LogicalRegister => Syndrome)` reprezentuje operację, która działa wspólnie na qubits w `LogicalRegister` i niektórych qubits pomocniczych, a następnie obejmuje pomiary qubits pomocniczych w celu wyodrębnienia `Syndrome` wartości reprezentującej `Result[]` te pomiary.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)