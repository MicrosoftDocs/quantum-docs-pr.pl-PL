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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="a8fdd-102">Przestarzały typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="a8fdd-102">Deprecated user defined type</span></span>

<span data-ttu-id="a8fdd-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a8fdd-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a8fdd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8fdd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8fdd-105">Rozpoznany przez kompilator atrybut używany do oznaczania typu lub jako przestarzałego.</span><span class="sxs-lookup"><span data-stu-id="a8fdd-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="a8fdd-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="a8fdd-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="a8fdd-107">NewName: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a8fdd-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a8fdd-108">Pełna nazwa typu lub, która ma zostać użyta.</span><span class="sxs-lookup"><span data-stu-id="a8fdd-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="a8fdd-109">Jest ustawiony na pusty ciąg, jeśli typ lub możliwy do nadania jest przestarzały bez podstawiania.</span><span class="sxs-lookup"><span data-stu-id="a8fdd-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>