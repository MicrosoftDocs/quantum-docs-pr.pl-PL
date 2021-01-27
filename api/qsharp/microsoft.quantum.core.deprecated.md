---
uid: Microsoft.Quantum.Core.Deprecated
title: Przestarzały typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832081"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="dc5dc-102">Przestarzały typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="dc5dc-102">Deprecated user defined type</span></span>

<span data-ttu-id="dc5dc-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="dc5dc-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="dc5dc-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dc5dc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dc5dc-105">Rozpoznany przez kompilator atrybut używany do oznaczania typu lub jako przestarzałego.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="dc5dc-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="dc5dc-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="dc5dc-107">NewName: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="dc5dc-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="dc5dc-108">Pełna nazwa typu lub, która ma zostać użyta.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="dc5dc-109">Jest ustawiony na pusty ciąg, jeśli typ lub możliwy do nadania jest przestarzały bez podstawiania.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>