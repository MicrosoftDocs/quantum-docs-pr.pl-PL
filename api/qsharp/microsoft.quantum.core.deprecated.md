---
uid: Microsoft.Quantum.Core.Deprecated
title: Przestarzały typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713272"
---
# <a name="deprecated-user-defined-type"></a>Przestarzały typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package [](https://nuget.org/packages/)


Rozpoznany przez kompilator atrybut używany do oznaczania typu lub jako przestarzałego.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="newname--string"></a>NewName: [ciąg](xref:microsoft.quantum.lang-ref.string)

Pełna nazwa typu lub, która ma zostać użyta.
Jest ustawiony na pusty ciąg, jeśli typ lub możliwy do nadania jest przestarzały bez podstawiania.