---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711424"
---
# <a name="message-function"></a><span data-ttu-id="7a95f-102">Message — funkcja</span><span class="sxs-lookup"><span data-stu-id="7a95f-102">Message function</span></span>

<span data-ttu-id="7a95f-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7a95f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7a95f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a95f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a95f-105">Rejestruje komunikat.</span><span class="sxs-lookup"><span data-stu-id="7a95f-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7a95f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7a95f-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="7a95f-107">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7a95f-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7a95f-108">Komunikat, który ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="7a95f-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a95f-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a95f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7a95f-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7a95f-110">Remarks</span></span>

<span data-ttu-id="7a95f-111">Określone zachowanie tej funkcji jest zależne od symulatora, ale w większości przypadków dany komunikat zostanie zapisany w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="7a95f-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>