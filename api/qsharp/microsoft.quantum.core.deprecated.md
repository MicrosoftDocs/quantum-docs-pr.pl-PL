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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="e775b-102">Przestarzały typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e775b-102">Deprecated user defined type</span></span>

<span data-ttu-id="e775b-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e775b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e775b-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e775b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e775b-105">Rozpoznany przez kompilator atrybut używany do oznaczania typu lub jako przestarzałego.</span><span class="sxs-lookup"><span data-stu-id="e775b-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="e775b-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="e775b-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="e775b-107">NewName: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e775b-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e775b-108">Pełna nazwa typu lub, która ma zostać użyta.</span><span class="sxs-lookup"><span data-stu-id="e775b-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="e775b-109">Jest ustawiony na pusty ciąg, jeśli typ lub możliwy do nadania jest przestarzały bez podstawiania.</span><span class="sxs-lookup"><span data-stu-id="e775b-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>