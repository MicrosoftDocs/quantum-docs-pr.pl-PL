---
uid: Microsoft.Quantum.Core.Deprecated
title: Przestarzały typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224092"
---
# <a name="deprecated-user-defined-type"></a>Przestarzały typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Rozpoznany przez kompilator atrybut używany do oznaczania typu lub jako przestarzałego.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="newname--string"></a>NewName: [ciąg](xref:microsoft.quantum.lang-ref.string)

Pełna nazwa typu lub, która ma zostać użyta.
Jest ustawiony na pusty ciąg, jeśli typ lub możliwy do nadania jest przestarzały bez podstawiania.