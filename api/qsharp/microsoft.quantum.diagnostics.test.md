---
uid: Microsoft.Quantum.Diagnostics.Test
title: Test typu zdefiniowanego przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712642"
---
# <a name="test-user-defined-type"></a>Test typu zdefiniowanego przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Atrybut rozpoznany przez kompilator używany do oznaczania testu jednostkowego.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="executiontarget--string"></a>ExecutionTarget: [ciąg](xref:microsoft.quantum.lang-ref.string)

