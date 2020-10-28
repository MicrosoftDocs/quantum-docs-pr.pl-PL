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
# <a name="test-user-defined-type"></a><span data-ttu-id="467d1-102">Test typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="467d1-102">Test user defined type</span></span>

<span data-ttu-id="467d1-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="467d1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="467d1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="467d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="467d1-105">Atrybut rozpoznany przez kompilator używany do oznaczania testu jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="467d1-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="467d1-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="467d1-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="467d1-107">ExecutionTarget: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="467d1-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

